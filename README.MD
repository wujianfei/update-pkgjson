### update-pkgjson

**模块**

- ```getNextVersion``` 获得下一个版本
- ```getUpdatedPackage``` 获取更新版本后的```package```内容
- ```getPublishPackage``` 获取发布包的内容

```shell
npm install update-pkgjson
```

**获取下一个版本**

```js
const { getNextVersion } = require('update-pkgjson')
const pkg = require('./package.json')
console.info(getNextVersion(pkg.version))
```

**获取更新版本后的package内容**

```js
const { getUpdatedPackage } = require('update-pkgjson')
const pkg = require('./package.json')
console.info(getUpdatedPackage(pkg))
```

**getPublishPackage**

```js
const { getPublishPackage } = require('update-pkgjson')
const pkg = require('./package.json')
const newPkg = getUpdatedPackage(pkg)

getPublishPackage(newPkg, {
  main: 'src/index.js', 
  homepage: '', 
  repository: {
    type: 'git',
    url: ''
  }, 
  bin: {
    '自定义命令': 'src/index.js'
  }
})
```

