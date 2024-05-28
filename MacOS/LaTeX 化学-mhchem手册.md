# LaTeX 化学入门-mhchem 手册中文翻译-内容逻辑重构

##### 相关

> - 官网：https://mhchem.github.io/MathJax-mhchem/
> - 继续深入 LaTeX 化学相关包
>     - https://github.com/latexstudio/LaTeX_in_Chemistry
>     - https://www.latexstudio.net/archives/8369

###### 目录

> - 简介 LaTeX 化学入门和 mhchem
>
> - 化学式
>
> -  化学计量数
>
> - 化学方程式
>
> - 细节

## 简介 LaTeX 化学入门 - mhchem

MHChem 是一种轻松编写精美化学方程式的工具。

例如：

$$\ce{Zn^2+  <=>[+ 2OH-][+ 2H+]  $\underset{\text{amphoteres Hydroxid}}{\ce{Zn(OH)2 v}}$  <=>[+ 2OH-][+ 2H+]  $\underset{\text{Hydroxozikat}}{\ce{[Zn(OH)4]^2-}}$}$$

### 使用 MHChem

Chemistry StackExchange：只需写 `$\ce{H2O}$` .

在其他带有 `MathJax` 的 `StackExchange` 网站上，每个问题/答案写 `$\require{mhchem}$` 一次就足够了。

Typora：写 `$\ce{H2O}$` 

Notion：写 `$$\ce{H2O}$$` 

Anki：写 `\(\ce{H2O}\)` 

## 化学式 chemical formulae

语法：`\ce{ }`

- `{ }` 括号里面默认字母后面带数字是下标
- 需要上标老实写 `^`
- 没有 LaTeX 的一个字符限制，可以多个字符，用空格隔开

$\ce{ H2O2 }$

`$\ce{ H2O2 }$`

$\ce{ CrO4^2- }$ = $\ce{ CrO4^{2-}}$

`$\ce{ CrO4^2- }$` = `$\ce{ CrO4^{2-}}$`

$\ce{ [AgCl2]- }$​

`$\ce{ [AgCl2]- }$`，（有时候，感觉还挺优化体验的）

### 希腊字母

- MathJax 和 KaTeX 都不支持直立的小写希腊字符。

- 希腊字符后面的空格将被忽略。这是标准的 TeX 行为。插入 `{}` 以获得所需的输出。

$\ce{ \mu-Cl }$

 `$\ce{ \mu-Cl }$`

$\ce{ [Pt(\eta^2-C2H4)Cl3]- }$​

`$\ce{ [Pt(\eta^2-C2H4)Cl3]- }$`

$\ce{\beta +}$

`\ce{ \beta + }`

$\ce{^40_18Ar + \gamma{} + \nu_e}$​

`\ce{ ^40_18Ar + \gamma{} + \nu_e }`

## 化学计量数 stoichiometric numbers

- 空格将被忽略
- 当排版需要空格时， `~` = 一个空格
- 整数直接写
- 小数直接写
- 分数也可以直接写，无需 LaTeX 的 `\frac 1 2`
- 小括号和中括号，也可以直接写
- 大括号需要转移 `\{ \}`
- 变量，MHChem 尝试自动识别斜体
    - 如果失败，可尝试用 `$斜体变量$` 包围（有点像嵌套 `$$` ）
    - 支持嵌套 `$\infty$` 之类的



$\ce{ 2H2O } = \ce{ 2 H2O }$​

`$\ce{ 2H2O } = \ce{ 2 H2O }$`

$\ce{ 0.5H2O }$​

`$\ce{ 0.5H2O }$`

$\ce{ 1/2 H2O }$

`\ce{ 1/2 H2O }`

$\ce{ (1/2) H2O }$

`$\ce{ (1/2) H2O }$`

$\ce{ n H2O}$

`$\ce{ n H2O}$`

$\ce{ X_{$i$}^{$x$} }$

`$\ce{ X_{$i$}^{$x$} }$`

$\ce{ Fe(CN)_{$\frac{6}{2}$} }$

`$\ce{ Fe(CN)_{$\frac{6}{2}$} }$`

$\ce{ $cis${-}[PtCl2(NH3)2] }$​

`$\ce{ $cis${-}[PtCl2(NH3)2] }$`

## 化学方程式 chemical equations (ce)

语法：`\ce{ }`

- 反应箭头

    - `->`、`<-`、`<->` 
    - `<-->`，$\ce{<-->}$
    - `<=>` ，$\ce{<=>}$​
    - `<=>>`、`<<=>` 左右箭头长短有区别，$\ce{<=>>}$
    - 箭头参数
        - `->[above][below]`
        - 每个箭头可以采用两个可选参数
        - 一个用于 above，一个用于 below
        - 参数，可以写直立文本、斜体数学

- 方程运算符

    - `+ - =` 直接写
    - `\pm` 加减

- 沉淀物和气体

    - `(v)` 小括号内字母 v
    - `(^)` 小括号内乘方 ^

- 物理单位

    - `$\pu{ 123 kJ }$`

    - `$\pu{ 123 mm2 }$`

    - 关于单位内的乘法有两种约定

        - `$\pu{ 123 J s }$`
        - `$\pu{ 123 J*s }$`

    - 关于分割有四种惯例

        - `$\pu{ 123 kJ/mol }$`
        - `$\pu{ 123 kJ//mol }$`
        - `$\pu{ 123 kJ mol-1 }$`
        - `$\pu{ 123 kJ*mol-1 }$`

    - 科学计数法

        - `$\pu{ 1.2e3 kJ }$`
        - `$\pu{ 1,2e3 kJ }$`
        - `$\pu{ 1.2E3 kJ }$`
        - `$\pu{ 1,2E3 kJ }$`

        

$\ce{ CO2 + C -> 2 CO}$​

`$\ce{ CO2 + C -> 2 CO}$`

$\ce{Hg^2+ ->[I^-] HgI2 ->[I-] [Hg^{II}I4]^2- }$

`$\ce{ Hg^2+ ->[I-] HgI2 ->[I-] [Hg^{II}I4]^2- }$`

$C_p[\ce{H2O(l)}] = \pu{75.3 J // mol K}$

`$C_p[ \ce{H2O(l)} ] = \pu{ 75.3 J // mol K }$`

$\ce{ SO4^2- + Ba^2+ -> BaSO4 (v) }$​

`$\ce{SO4^2- + Ba^2+ -> BaSO4 (v) }$`

$\ce{x Na(NH4)HPO4 ->[\Delta] (NaPO3)_x + x NH3 ^ + x H2O}$​

`$\ce{ x Na(NH4)HPO4 ->[\Delta] (NaPO3)_x + x NH3 ^ + x H2O }$`

## 小括号、中括号、大括号 parentheses, brackets, braces

对于大括号， `\left` 宏 `\right` 需要在相同的数学环境中，因此您可能需要 `$` 输入 `\ce` `\ce` ，但这没关系。

$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$

`$\ce{CH4 + 2 $\left( \ce{O2 + 79/21 N2} \right)$}$`

## 直立文本，转义解析 upright text, escape parsing

用 `{...}` .

使用相同的机制，您可以逃避解析，例如，如果您需要一个简单的连字符（不应成为绑定）。

$\ce{ {Gluconic Acid} + H2O2 }$​

`$\ce{ {Gluconic Acid} + H2O2 }$`

$\ce{ X_{{red}} }$​

`$\ce{ X_{{red}} }$`

$\ce{ {(+)}_589{-}[Co(en)3]Cl3 }$

`$\ce{ {(+)}_589{-}[Co(en)3]Cl3 }$`

## 氧化态 oxidation states

$\ce{ Fe^{II}Fe^{III}2O4 }$​

`$\ce{ Fe^{II}Fe^{III}2O4 }$`

## 不成对的电子，自由基点 unpaired electrons, radical dots

- `.`

$\ce{ OCO^{.-} }$​

`$\ce{ OCO^{.-} }$`

$\ce{ NO^{(2.)-} }$​

`$\ce{ NO^{(2.)-} }$`

## 核素、同位素 nuclides, isotopes

- 上标是属于左元素还是右元素可能不明确
- 有自动检测（仅数字 = 质量数 = 属于右侧）
- 但要确保您可以键入 `{}` 作为分隔符

$\ce{ ^{227}_{90}Th+ } = \ce{ ^227_90Th+ }$

`$\ce{ ^{227}_{90}Th+ } = \ce{ ^227_90Th+ }$`

$\ce{ ^{0}_{-1}n^{-} } = \ce{ ^0_-1n-}$

`$\ce{ ^{0}_{-1}n^{-} } = \ce{ ^0_-1n-}$`

$\ce{ H{}^3HO } = \ce{ H^3HO }$​

`$\ce{ H{}^3HO } = \ce{ H^3HO }$`

## 聚合状态 states of aggregation

（latex 尚不完全支持）

$\ce{ H2(aq) }$​

`$\ce{ H2(aq) }$`

$\ce{ CO3^2-_{(aq)} }$​

`$\ce{ CO3^2-_{(aq)} }$`

$\ce{ NaOH(aq,$\infty$) }$

`$\ce{ NaOH(aq,$\infty$) }$`

## 晶体系统 crystal systems

（latex 尚不完全支持）

$\ce{ ZnS($c$) }$

`$\ce{ ZnS($c$) }$`

$\ce{ZnS(\ca$c$)}$

`\ce{ ZnS(\ca$c$) }`

## 简单有机物结构式 bonds

MHChem 试图区分 `\ce{-}` 应该是键、电荷还是连字符。

- `\bond{-}`、`\bond{1}`
- `\bond{=}`、`\bond{2}`
- `\bond{#}`、`\bond{3}`
- `\bond{~}`、`\bond{~ - ~}`、`\bond{~ ~ ~}`
- `\bond{...}`、`\bond{....}`
- `\bond{->}`、`\bond{<-}`

$\ce{ A\bond{-}B\bond{=}C\bond{#}D }$

`$\ce{ A\bond{-}B\bond{=}C\bond{#}D }$`

$\ce{ A\bond{~--}B\bond{~=}C\bond{-~-}D }$

`$\ce{ A\bond{~--}B\bond{~=}C\bond{-~-}D }$`

$\ce{ A\bond{...}B\bond{....}C }$

`$\ce{ A\bond{...}B\bond{....}C }$`

$\ce{ A\bond{->}B\bond{<-}C }$

`$\ce{ A\bond{->}B\bond{<-}C }$`

## 加成化合物 addition compounds 

- `*`、`.`

$\ce{ KCr(SO4)2*12H2O } = \ce{ KCr(SO4)2.12H2O } = \ce{ KCr(SO4)2 * 12 H2O }$

`\ce{ KCr(SO4)2*12H2O } = \ce{ KCr(SO4)2.12H2O } = \ce{ KCr(SO4)2 * 12 H2O }`

## kröger-vink notation

$\ce{ Li^x_{Li,1-2x}Mg^._{Li,x}$V$'_{Li,x}Cl^x_{Cl} }$

`$\ce{ Li^x_{Li,1-2x}Mg^._{Li,x}$V$'_{Li,x}Cl^x_{Cl} }$`

$\ce{O''_{i,x}}$​

`$\ce{ O''_{i,x} }$`

$\ce{ M^{..}_i }$

`$\ce{ M^{..}_i }$`

$\ce{ $V$^{4'}_{Ti} }$

`$\ce{ $V$^{4'}_{Ti} }$`

$\ce{ V_{V,1}C_{C,0.8}$V$_{C,0.2} }$

`$\ce{ V_{V,1}C_{C,0.8}$V$_{C,0.2} }$`

## 其他符号和快捷方式

Excited state 激发态

$\ce{ NO^* }$

`$\ce{ NO^* }$`

Orbitals 轨道

$\ce{ 1s^2-N }$

`$\ce{ 1s^2-N }$`

$\ce{ n-Pr }$

`$\ce{ n-Pr }$`

$\ce{ \ca Fe }$

`$\ce{ \ca Fe }$`

$\ce{ A, B, C; F }$

`$\ce{ A, B, C; F }$`





