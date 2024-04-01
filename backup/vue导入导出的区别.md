## import {xxx} from "path" 
用于导入模块中导出的一个或多个特定的绑定（变量、函数、类等）。
这种方式用于导入非默认导出的成员，且需要使用花括号{}包裹成员名称。
例如，如果模块path导出了多个绑定（如export const a = 1; export function b() {}），可以使用import {a, b} from "path"来导入这些特定的绑定。

## import xxx from "path" 
用于导入模块的默认导出。每个模块只能有一个默认导出，使用此语法时不需要花括号。
例如，如果模块path有一个默认导出（如export default function() {}或export default class {}），可以使用import xxx from "path"来导入这个默认导出，其中xxx是这个导入的本地名称。

## 关于export的default、declare和const
export default: 这是ES6模块化规范中用于指定模块的默认导出的关键字。每个模块只能有一个默认导出。默认导出可以是一个函数、类、对象或任何其他有效的JavaScript表达式。**导入时，可以使用任意名称来引入**。

export declare: 这个关键字主要用在TypeScript中，而不是JavaScript。它用于声明变量、函数、类等的类型，而不是创建它们。这常用于声明外部环境中已存在的全局变量的类型，或在.d.ts文件（TypeScript类型声明文件）中声明模块的导出类型。

export const: 这是用来声明变量的，其值不可重新赋予。在模块化中，const可以用来定义模块级别的常量，可以通过export关键字导出这些常量，使它们可以在其他模块中被导入和使用。

export default和export const直接参与模块的导出和导入机制，而declare主要用于TypeScript中声明已存在的变量或模块接口的类型，而不直接参与JavaScript的模块化导出导入操作。