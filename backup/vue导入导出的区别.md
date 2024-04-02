## import {xxx} from "path" 
用于导入模块中导出的一个或多个特定的绑定（变量、函数、类等）。
这种方式用于导入非默认导出的成员，且需要使用花括号{}包裹成员名称。
例如，如果模块path导出了多个绑定（如export const a = 1; export function b() {}），可以使用import {a, b} from "path"来导入这些特定的绑定。

## import xxx from "path" 
用于导入模块的默认导出。每个模块只能有一个默认导出，使用此语法时不需要花括号。
例如，如果模块path有一个默认导出（如export default function() {}或export default class {}），可以使用import xxx from "path"来导入这个默认导出，其中xxx是这个导入的本地名称。

## import type xxx或{xxx} from "path"
用于导入接口类型

## 关于export
export default xxx: 这是ES6模块化规范中用于指定模块的默认导出的关键字。每个模块只能有一个默认导出。默认导出可以是一个函数、类、对象或任何其他有效的JavaScript表达式。**导入时，可以使用任意名称来引入**。

export const/function/class/interface/type: 分别用于导出常量，函数，类，接口和类型别名，使它们可以在其他模块中被导入和使用。