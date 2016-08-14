# Code Modificators

> Code modificators are scripts that traverse javascript files and can modify it's contents programatically. 

## JSCodeshift

> [JSCodeShift](https://github.com/facebook/jscodeshift) is a code modificator tool that wraps Recast with a JQuery-like API. 
> 
> It works by reading the javascript file text as input to turn it into AST (Abstract Syntax Trees)

An **identifier** to JSCodeShift is like a **selector** to CSS

> Note: pascal case version of node type **Identifier** is used for checking the type of the node and camel case version of node type **identifier** is used to create a node of that type.

### Reference
- [app.jscodeshift API](https://github.com/facebook/jscodeshift/wiki/jscodeshift-Documentation)
- [toSource options](https://github.com/benjamn/recast/blob/1a8c04358d396099fd428c1bed27cc3d91b1d1d9/lib/options.js)
- [ast-types examples](https://github.com/benjamn/ast-types/tree/master/def)

To create an abstract tree run `app.jscodeshift(file.source)`

## AST

key | Definition
-- | --
**Program** | Program
**ExpressionStatement** | a function or any expression eg `a + b`
**BinaryExpression** | is a type of **ExpressionStatement** that includes only two values
**Identifier** | is used for names of variables, functions, methods, object keys, etc
**TemplateLiteral** | string template 
**quasis** | Template elements between `${}` expressions



## Tools
- [ASTExplorer](https://astexplorer.net/) to explore the AST of any code snippet

## tutorials

- [How to write codemods](https://vramana.github.io/blog/2015/12/21/codemod-tutorial/)

