# DEPRECATION NOTICE

> **⚠️ WARNING: This project is no longer maintained.**
>
> This repository is archived and is not accepting any new issues, pull requests, or updates.
> 
> **Please consider using the following alternative:**
> - [Ant-Design Jalali/Hijri DatePicker](https://github.com/masoudit/antd-jalali-plus)
> - [Ant-Design Jalali DatePicker](https://github.com/saeedrahimi/antd-jalali)

---

# Jalali dates and times for ant-design

This is a fork of [jalali-moment](https://github.com/fingerpich/jalali-moment) and it's modified just to use with [ant-design](https://github.com/ant-design/ant-design) so if you want use it just for jalali dates and time you should go to jalali-moment page and see the original docs

Read this in other languages: [فارسی](./README.fa.md)

It was a fork of [moment-jalali](https://github.com/jalaali/moment-jalaali) but the main goal of this repository is to facilitate converting any library using [moment.js](https://momentjs.com/) to be compatible with jalali calendar system.
[List of packages](https://www.npmjs.com/browse/depended/jalali-moment) use [jalali-moment](https://github.com/fingerpich/jalali-moment) to convert calendar system.

[![MIT License][license-image]][license-url]
[![NPM version][npm-version-image]][npm-url]

> Please take a look at [day.js](https://github.com/iamkun/dayjs), [jalaliday](https://github.com/alibaba-aero/jalaliday) module.

## How to

- [Install](#install)
- Use jalali moment in

  - [ant-design](#ant-design)

  This plugin provides using jalali and gregorian calendar system together
  on [momentjs](https://momentjs.com/docs/) api.

  `.locale('fa');` it will use jalali calendar system

  `.locale('any other locale');` it will use gregorian calendar system

## Introduction

jalali(Persian) calendar is a solar calendar system. It gains approximately 1 day on the Julian calendar every 128 years. [Read more on Wikipedia](http://en.wikipedia.org/wiki/Jalali_calendar).

Calendar conversion is based on the [algorithm provided by Kazimierz M. Borkowski](http://www.astro.uni.torun.pl/~kb/Papers/EMP/PersianC-EMP.htm) and has a very good performance.

This plugin adds Jalali (Persian, Khorshidi, Shamsi) calendar system to [moment.js](http://momentjs.com) library.

## Install

Install via **npm**

```shell
npm install antd-jalali-moment -S
```

Install via **yarn**

```shell
yarn add antd-jalali-moment
```

Install via **bower**

```shell
bower install antd-jalali-moment --save
```

change webpack config and use alias for changing moment to antd-jalali-moment.

if you use react-app-rewired you can use this config.overrides.js

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

## Usage

#### ant-design

Install it via npm or yarn then wrap your App component in [LocaleProvider](https://ant.design/components/locale-provider/) component.

```js
import React from "react";
import ReactDOM from "react-dom";
import { LocaleProvider } from "antd";
import fa_IR from "antd/lib/locale-provider/fa_IR";
import "moment/locale/fa";
import moment from "moment";
import App from "./App";

moment.locale("fa");

ReactDOM.render(
  <LocaleProvider locale={fa_IR}>
    <App />
  </LocaleProvider>,
  document.getElementById("root")
);
```

Basically with installing this package you bring jalali dates and time to LocaleProvider component so if you use redux or else and change language and locale at any time, dates and time goes back to original date system.

## API

for using the original jalali-moment api read the original docs [HERE](https://github.com/fingerpich/jalali-moment).

[license-image]: http://img.shields.io/badge/license-MIT-blue.svg?style=flat
[license-url]: LICENSE
[npm-url]: https://npmjs.org/package/antd-jalali-moment
[npm-version-image]: http://img.shields.io/npm/v/antd-jalali-moment.svg?style=flat
