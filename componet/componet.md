动态加载组件的四种方式：

1、使用import导入组件，可以获取到组件
```
var name = 'system';
var myComponent =() => import('../components/' + name + '.vue');
var route={
    name:name,
    component:myComponent
}
```

2、使用import导入组件，直接将组件赋值给componet

```
var name = 'system';
var route={
    name:name,
    component :() => import('../components/' + name + '.vue');
}
```

3、使用require 导入组件，可以获取到组件

```
var name = 'system';
var myComponent = resolve => require.ensure([], () => resolve(require('../components/' + name + '.vue')));
var route={
    name:name,
    component:myComponent
}
```
4、使用require 导入组件，直接将组件赋值给componet

```
var name = 'system';
var route={
    name:name,
    component(resolve) {
		require(['../components/' + name + '.vue'], resolve)
	}
}
```

