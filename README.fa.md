<div dir="auto">
  
# تاریخ جلالی برای ant-design

کتابخانه ای برای افزودن تاریخ شمسی به ant-design

این کتابخانه یک fork از کتابخانه اصلی [jalali-moment](https://github.com/fingerpich/jalali-moment) است.

## نحوه

## نصب

<div dir="ltr">
  
```shell
npm install antd-jalali-moment -S
```
  
</div> 

یا

<div dir="ltr">
  
```shell
yarn add antd-jalali-moment
```
  
</div>

## استفاده

بعد از نصب کافی است این کتابخانه را به عنوان alias برای moment قرار دهید

اگر از react-app-rewired استفاده میکنید میتوانید از فایل زیر برای تغییر تنظیمات استفاده کنید.
  
<div dir="ltr">

#### config.overrides.js
  
```js
const { injectBabelPlugin } = require("react-app-rewired");
const rewireLess = require("react-app-rewire-less");

module.exports = function override(config, env) {
  config = injectBabelPlugin(
    ["import", { libraryName: "antd", libraryDirectory: "es", style: "css" }],
    config
  );
  config = injectBabelPlugin(
    ["import", { libraryName: "antd", style: true }],
    config
  );
  config = injectBabelPlugin(["syntax-dynamic-import"], config);
  config.resolve.alias["moment"] = "antd-jalali-moment"; // this is where we use alias
  return config;
};
```
    
</div>
  
</div>
