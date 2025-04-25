# wx-wasm-bindgen

基于[rustwasm/wasm-bindgen](https://github.com/rustwasm/wasm-bindgen)做了微信小程序兼容性改造，主要修改点如下：

1. 禁用网络下载 wasm 文件功能

- 避免生成依赖网络的代码（如 import.meta.url 和 fetch wasm）。

2. 将`WebAssembly`替换为`WXWebAssembly`

- 在`replace_wasm_names`函数中，遍历输出目录下所有 .js 和 .ts 文件，将文件内容中的 WebAssembly 字符串替换为 WXWebAssembly，以适配微信小程序的自定义全局对象。

### 关联上游项目

[rustwasm/wasm-bindgen](https://github.com/rustwasm/wasm-bindgen)

### install

```bash
cargo install --git https://github.com/BenLocal/wx-wasm-bindgen
```

### install [wx-wasm-pack](https://github.com/BenLocal/wx-wasm-pack)

```bash
cargo install --git https://github.com/BenLocal/wx-wasm-pack
```
