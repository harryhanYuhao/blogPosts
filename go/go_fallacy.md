# The fallacy of go

Here is a list of go features I can not bear with. 

**All** import and variables must be used, otherwise the compiler panics. 
Go team has emphasized that there is absolutely [no way around it](https://golang.org/doc/faq#unused_variables_and_imports). 

> The presence of an unused variable may indicate a bug, while unused imports just slow down compilation, an effect that can become substantial as a program accumulates code and programmers over time. For these reasons, Go refuses to compile programs with unused variables or imports, trading short-term convenience for long-term build speed and program clarity. 
> ...
> Some have asked for a compiler option to turn those checks off or at least reduce them to warnings. Such an option has not been added, though, because compiler options should not affect the semantics of the language and because the Go compiler does not report warnings, only errors that prevent compilation. 

Such arrogant words! Therefore, an eye for an eye, I rebuke and resent such rational most fiercely. 

For any practical purpose it is natural, when debugging, to comment out certain variables, or to include a long and verbose import line at a time of convenience. I claim every programmer in their career has done this. But Go compile will refuse to compile in these situations. 
In reality this feature, for most parts, only wasted developper's time. 

Here are more discussions on this issue: 

https://github.com/golang/go/issues/43729
https://groups.google.com/g/golang-nuts/c/obbh9Ak-LzQ/m/UgLmiNfCLnwJ?pli=1
