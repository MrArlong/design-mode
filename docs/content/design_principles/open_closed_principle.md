# 开闭原则

开闭原则，The Open-Closed Principle，简称 OCP，是指软件实体（类、模块、函数等）应该可以扩展，但是不可以修改。即对于扩展是开放的，对于更改是封闭的。通俗来说就是对于要增加的新功能或要调整的改动，尽量扩展新代码而不是修改已有代码。

**使用动机**

面对需求改变可以保持相对稳定，使得系统可以在第一个版本以后不断推出新的版本。

**如何使用**

通过对以下可能时机的变化，创建抽象，隔离以后发生的同类变化。

- 在开发工作展开前预测可能的变化。

- 或展开不久后知道可能发生的变化。

- 或当实际需要发生时带来的变化。

**使用原则**

- 仅对程序中呈现出频繁变化的部分做出抽象。
- 不要刻意对每个部分进行抽象，拒绝不成熟的抽象，它和抽象本身一样重要。

**使用示例**

以一个加法器为例。

当我们在接到这个需求时，就可以很容易地想到以后可能需要减法、乘法、除法等等运算。所以，我们在开发的时候就可以先把「加法」抽象成一个类，这样，以后需要其他运算时，只要增加一个类即可。

实际做的时候我们可能会发现用户输入的可能是个表达式，不一定是两个数字，有可能是三个数字，还有可能有括号。这时候我们可能会写一个四则混合运算解析器类。以后如果需要解析其他表达式（如复数），则只需增加对应的类。

好不容易做完了，突然又来了新需求，需要做一个字符串的加法（即拼接），我们假设 API 不变。此时，我们可能需要设计一个输入表达式判断器类，用于判断是数字还是字符串的运算。我们还需要对原来的代码进行一些调整，以便 API 进来的输入能够首先通过判断器。