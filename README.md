
# element issues

1. 动态/循环 表单校验必须 循环的对象必须是  form 中的 属性

2. **值赋上去 vue devtools有值 页面不回显的原因是：没有使用 $set , 不是响应式**

3. el-form 有校验但是没有执行回调的原因是：没有在validate值中执行callback

4. el-dialog 中的 el-form 有时候会莫名其妙校验的原因是 open dialog 时值发生了改变（如 第一次打开时，默认值时 undefined， 而 el-select 多选会导致 undefined 变为 [], 这样值就被改变了，所以触发了校验，）