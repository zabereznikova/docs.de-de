---
title: Überladbare Operatoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: 850b10958446193026506418c57d7f565c98b714
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452769"
---
# <a name="overloadable-operators-c-programming-guide"></a>Überladbare Operatoren (C#-Programmierhandbuch)

C# ermöglicht benutzerdefinierten Typen, mithilfe des Schlüsselworts [operator](../../language-reference/keywords/operator.md) Operatoren durch das Definieren von statischen Memberfunktionen zu überladen. Nicht alle Operatoren können überladen werden und weisen andere Einschränkungen auf. Eine entsprechende Auflistung finden Sie in dieser Tabelle:

| Operatoren | Überladbarkeit |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/boolean-logical-operators.md#logical-negation-operator-), [~](../../language-reference/operators/bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/keywords/true-false-operators.md), [false](../../language-reference/keywords/true-false-operators.md)|Diese unären Operatoren können überladen werden.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-), [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-), [^](../../language-reference/operators/boolean-logical-operators.md#logical-exclusive-or-operator-), [\<\<](../../language-reference/operators/bitwise-and-shift-operators.md#left-shift-operator-), [>>](../../language-reference/operators/bitwise-and-shift-operators.md#right-shift-operator-)|Diese binären Operatoren können überladen werden.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/comparison-operators.md#less-than-operator-), [>](../../language-reference/operators/comparison-operators.md#greater-than-operator-), [\<=](../../language-reference/operators/comparison-operators.md#less-than-or-equal-operator-), [>=](../../language-reference/operators/comparison-operators.md#greater-than-or-equal-operator-)|Die Vergleichsoperatoren können überladen (beachten Sie jeden Hinweis im Anschluss an diese Tabelle) werden.|
|[&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)|Die bedingten logischen Operatoren können nicht überladen werden. Sie werden jedoch mithilfe von `&` und <code>&#124;</code> ausgewertet, die überladen werden können.|
|[&#91;&#93;](../../language-reference/operators/member-access-operators.md#indexer-operator-)|Der Arrayindizierungsoperator kann nicht überladen werden. Sie können jedoch [Indexer](../indexers/index.md) definieren.|
|[(T)x](../../language-reference/operators/invocation-operator.md)|Der Umwandlungsoperator kann nicht überladen werden. Sie können jedoch neue Konvertierungsoperatoren definieren (siehe [explicit](../../language-reference/keywords/explicit.md) und [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [&#124;=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [^=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [\<\<=](../../language-reference/operators/bitwise-and-shift-operators.md#compound-assignment), [>>=](../../language-reference/operators/bitwise-and-shift-operators.md#compound-assignment)|Zuweisungsoperatoren können nicht explizit überladen werden. Wenn Sie einen binären Operator überladen, wird der zugehörige Zuweisungsoperator jedoch, sofern er vorhanden ist, auch implizit überladen. Wenn `+=` beispielsweise mit `+` ausgewertet wird. Selbiger kann überladen werden.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operators.md#member-access-operator-), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/member-access-operators.md#invocation-operator-), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|Diese Operatoren können nicht überladen werden.|

> [!NOTE]
> Die Vergleichsoperatoren müssen, sofern sie überladen sind, paarweise überladen werden. Beim Überladen von `==` muss `!=` demnach ebenfalls überladen werden. Das Gegenteil trifft ebenfalls zu, wenn das Überladen von `!=` eine Überladung von `==` erfordert. Das gleiche gilt für die Vergleichsoperatoren `<`, `>`, `<=` und `>=`.

Informationen zum Überladen eines Operators finden Sie im Keyword-Artikel [Operator](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Anweisungen, Ausdrücke und Operatoren](index.md)
- [Operatoren](operators.md)
- [C#-Operatoren](../../language-reference/operators/index.md)
- [Why are overloaded operators always static in C#? (Warum sind überladene Operatoren in C# immer statisch?)](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
