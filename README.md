
# element issues

1. 动态/循环 表单校验必须 循环的对象必须是 form 中的 属性（不能不在from中）

2. **值赋上去 vue devtools有值 页面不回显的原因是：没有使用 $set , 不是响应式**

3. el-form 有校验但是没有执行回调的原因是：没有在validate值中执行callback

4. el-form 校验部分字段时，数组有几位，就会回调几次
```js
const validateList = [];
this.$refs.resetPwForm.validateField(['key1', 'key2'], (valid) => {
   validateList.push(valid);  // valid 校验成功就为 '', 否则就是 message
});
if(validateList.every(v => v === '')) {
  // do something ... 
}
```

5. el-dialog 中的 el-form 有时候会莫名其妙校验的原因是 open dialog 时值发生了改变（如 第一次打开时，默认值时 undefined， 而 el-select (change事件) 多选会导致 undefined 变为 [], 这样值就被改变了，所以触发了校验，对于这种问题，我们赋值时赋值为组件支持的值就行了)）

6. **v-if 和 v-else 使用的时候注意是否要加key** 否则会导致 节点 重用，这会导致例如表单的状态会重用
