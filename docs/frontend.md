# 前端编码规范

## HTML 规范

### 页面语言 LANG

使用属性值 `cmn-Hans-CN`（简体, 中国大陆），避免因浏览器自动翻译造成的中文改变。

`<html lang="cmn-Hans-CN">`

### HTML 代码大小写

HTML 标签名、类名、标签属性和大部分属性值统一用小写

`<div class="demo"></div>`

## 图片规范

### 图片格式及大小

Icon 等使用 ... 格式，大小不超过 ...

内容图使用 ... 格式

背景图使用 ... 格式

## CSS 规范

### 属性书写顺序

建议遵循以下顺序：

1. 布局定位属性：display / position / float / clear / visibility / overflow
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

```css
.jdc {
    display: block;
    position: relative;
    float: left;
    width: 100px;
    height: 100px;
    margin: 0 10px;
    padding: 20px 0;
    font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
    color: #333;
    background: rgba(0,0,0,.5);
    -webkit-border-radius: 10px;
    -moz-border-radius: 10px;
    -o-border-radius: 10px;
    -ms-border-radius: 10px;
    border-radius: 10px;
}
```

### [Ant Design 修改样式](https://pro.ant.design/docs/style-cn)

由于脚手架默认使用 CSS Modules 模块化方案，在下面的样式文件中，`.title` 只会在本文件生效，你可以在其他任意文件中使用同名选择器，也不会对这里造成影响。不过有的时候，我们就是想要一个全局生效的样式呢？可以使用 `:global`

```less
// example.less
.title {
  color: @heading-color;
  font-weight: 600;
  margin-bottom: 16px;
}

/* 定义全局样式 */
:global(.text) {
  font-size: 16px;
}

/* 定义多个全局样式 */
:global {
  .footer {
    color: #ccc;
  }
  .sider {
    background: #ebebeb;
  }
}
```

**全局样式**

在 `src/global.less` 文件中，可以进行一些通用设置，这边的优先级最高，将覆盖全局样式。

**覆盖组件样式**

```less
// TestPage.less
.customSelect {
  :global {
    .ant-select-selection {
      max-height: 51px;
      overflow: auto;
    }
  }
}
```

- 引入的 antd 组件类名没有被 CSS Modules 转化，所以被覆盖的类名 `.ant-select-selection` 必须放到 `:global` 中。
- 因为上一条的关系，覆盖是全局性的。为了防止对其他 Select 组件造成影响，所以需要包裹额外的 className 限制样式的生效范围。

## 命名规范



## React 规范

### 数据流方案

使用 [DvaJS](https://dvajs.com/guide/getting-started.html) 作为数据流方案，请定义 model.js 作为数据管理的模块化，定义 service.js 存储异步请求，使用 connect 方法连结 model 和组件。

