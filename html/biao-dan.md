> input 背景提示
```
<input placeholder="提示文字即可">


input::-webkit-input-placeholder {
    /* placeholder颜色  */
    color: #aab2bd;
    /* placeholder字体大小  */
    font-size: 12px;
    /* placeholder位置  */
    text-align: left;
}
```
> input 显示的内容
```
<input value="显示内容">
```


> action 执行请求的提交地址 onsubmit执行提交前的 js 函数。 method 请求方法
```
<form method="post" id="bug-report-form" action="url" onsubmit="return checkInput()" method="post">
</form>
```