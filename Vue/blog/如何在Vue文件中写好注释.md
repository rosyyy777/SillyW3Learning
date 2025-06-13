# 如何在Vue文件中写好注释

## 一、头部注释

Vue文件通常分为三个独立的部分：template、script和style。对于头部注释，推荐写在script部分的顶端，利用Javascript的多行注释风格。

```javascript
<script>
/**
 * @name: UserLogin
 * @description: 用户登录组件
 * @author: YourName
 * @date: 2023-10-01
 * @props: 
 *   - username: 初始用户名 (String)
 *   - remember: 记住登录状态 (Boolean)
 * @emits: 
 *   - success: 登录成功时触发
 *   - fail: 登录失败时触发
 */
export default {
  // ...
}
</script>
```

## 二、变量注释规范

**基本类型变量**：用单行注释

```javascript
const count = ref(0) // 计数器，初始值为 0
const disabled = ref(true) // 禁用状态，默认为 true
```

**复杂对象/响应式变量**：用 JSDoc 多行注释

```javascript
/**
 * 表单数据对象
 * @property {string} name - 用户名（必填）
 * @property {number} age - 年龄（范围 0-120）
 */
const formData = reactive({
  name: '',
  age: 18
})
```

**Ref 类型**：注明用途和初始值

```javascript
/**
 * 页面加载状态
 * @type {import('vue').Ref<boolean>}
 */
const isLoaded = ref(false)
```

### 三、函数注释规范（JSDoc）

#### 1. **基础函数**：描述 + 参数 + 返回值

```javascript
/**
 * 计算两个数字的和
 * @param {number} a - 第一个加数
 * @param {number} b - 第二个加数
 * @returns {number} 两数之和
 */
function add(a, b) {
  return a + b
}
```

#### 2. **操作 Ref 的函数**：注明副作用

```javascript
/**
 * 重置表单数据
 * @sideeffect 会修改 formData 的所有字段
 */
function resetForm() {
  Object.assign(formData, { name: '', age: 18 })
}
```

#### 3. **异步函数**：标记 Promise 和错误

```javascript
/**
 * 获取用户列表
 * @throws {Error} 当 API 请求失败时抛出
 * @returns {Promise<User[]>} 用户数组
 */
async function fetchUsers() {
  const res = await api.get('/users')
  return res.data
}
```

---

## 四、变量与函数组合逻辑

在 JavaScript（尤其是 Vue 3 的 Composition API 或 React Hooks）中，**如何组织 `ref`/`reactive` 变量和函数注释**是一个常见的工程化问题。

#### **逻辑相关性分组**（推荐）

将变量和操作它们的函数放在一起，形成独立的逻辑单元。这是 Composition API 的设计初衷。  
```javascript
// ✅ 推荐：按功能分组
// ------------------------ 用户数据逻辑 ------------------------
const user = ref(null) // 当前登录用户信息
const isLoading = ref(false) // 加载状态

/** 获取用户数据 */
async function fetchUser() {
  isLoading.value = true
  user.value = await api.get('/user')
  isLoading.value = false
}

// ------------------------ 表单逻辑 ------------------------
const formData = reactive({
  name: '',
  age: 18
})

/** 提交表单 */
function submitForm() {
  if (!formData.name) return alert('Name is required')
  // ...
}
```

 #### **变量集中声明**（传统方式）

适合简单组件，但逻辑复杂时容易混乱：
```javascript
// ⚠️ 简单场景可用，复杂时难维护
const user = ref(null)
const isLoading = ref(false)
const formData = reactive({ /* ... */ })

// 函数集中在后面
async function fetchUser() { /* ... */ }
function submitForm() { /* ... */ }
```

---

## 四、特殊场景注释技巧

#### 1. **泛型 Ref**（TypeScript 或 JSDoc）

```javascript
/** @type {Ref<{ id: number; name: string }>} */
const currentUser = ref(null)
```

#### 2. **依赖注入**（Provide/Inject）
```javascript
// provider.js
/** 注入的全局配置 */
const config = ref({ theme: 'dark' })
provide('config', config)

// consumer.js
/** @type {Ref<{ theme: string }>} */
const config = inject('config')
```

#### 3. **TODO/FIXME 标记**
```javascript
const tempData = ref([]) // FIXME: 临时方案，需替换为持久化存储
```

---

### 五、工具支持
1. **ESLint**：配置 [jsdoc](https://github.com/gajus/eslint-plugin-jsdoc) 规则强制注释规范。
2. **TypeScript**：直接使用 TS 类型替代部分 JSDoc。
3. **VSCode 插件**：
   - **Document This**：自动生成 JSDoc。
   - **Todo Tree**：高亮 TODO/FIXME。

---

## 总结：最佳实践

1. **组织原则**：  
   - 优先按逻辑分组（变量 + 相关函数）。  
   - 复杂组件可用 `// ------ 分组标题 ------` 分隔。  
2. **注释原则**：  
   - 公共 API 用完整 JSDoc，内部变量用单行注释。  
   - 始终注明 `ref/reactive` 的初始结构和类型。  
3. **维护性**：  
   - 用 `@sideeffect` 标记会修改响应式变量的函数。  
   - 用 `@deprecated` 标记即将废弃的变量。  

通过这种结构，即使代码量增长，也能保持可读性和可维护性。