
# element issues

1. 动态/循环 表单校验必须 循环的对象必须是  form 中的 属性

2. **值赋上去 vue devtools有值 页面不回显的原因是：没有使用 $set , 不是响应式**

3. el-form 有校验但是没有执行回调的原因是：没有在validate值中执行callback