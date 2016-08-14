# Code Modificators



> [JSCodeShift](https://github.com/facebook/jscodeshift) is a code modificator tool that wraps Recast with a JQuery-like API. Code modificators are scripts that traverse javascript files and can modify it's contents programatically. 
> 
> It works by reading the javascript file text as input to turn it into AST (Abstract Syntax Trees)

An **identifier** to JSCodeShift is like a **selector** to CSS

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

