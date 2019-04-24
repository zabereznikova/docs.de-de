---
title: Überladbare Operatoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: d0a5555bbe68aa82218c1dbe3d24705b26aff9c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296575"
---
# <a name="overloadable-operators-c-programming-guide"></a>Überladbare Operatoren (C#-Programmierhandbuch)

C# ermöglicht benutzerdefinierten Typen, mithilfe des Schlüsselworts [operator](../../language-reference/keywords/operator.md) Operatoren durch das Definieren von statischen Memberfunktionen zu überladen. Nicht alle Operatoren können überladen werden und weisen andere Einschränkungen auf. Eine entsprechende Auflistung finden Sie in dieser Tabelle:

| Operatoren | Überladbarkeit |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/boolean-logical-operators.md#logical-negation-operator-), [~](../../language-reference/operators/bitwise-complement-operator.md), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/keywords/true-false-operators.md), [false](../../language-reference/keywords/true-false-operators.md)|Diese unären Operatoren können überladen werden.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/and-operator.md), [&#124;](../../language-reference/operators/or-operator.md), [^](../../language-reference/operators/xor-operator.md), [\<\<](../../language-reference/operators/left-shift-operator.md), [>>](../../language-reference/operators/right-shift-operator.md)|Diese binären Operatoren können überladen werden.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/less-than-operator.md), [>](../../language-reference/operators/greater-than-operator.md), [\<=](../../language-reference/operators/less-than-equal-operator.md), [>=](../../language-reference/operators/greater-than-equal-operator.md)|Die Vergleichsoperatoren können überladen (beachten Sie jeden Hinweis im Anschluss an diese Tabelle) werden.|
|[&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)|Die bedingten logischen Operatoren können nicht überladen werden. Sie werden jedoch mithilfe von `&` und <code>&#124;</code> ausgewertet, die überladen werden können.|
|[&#91;&#93;](../../language-reference/operators/index-operator.md)|Der Arrayindizierungsoperator kann nicht überladen werden. Sie können jedoch [Indexer](../indexers/index.md) definieren.|
|[(T)x](../../language-reference/operators/invocation-operator.md)|Der Umwandlungsoperator kann nicht überladen werden. Sie können jedoch neue Konvertierungsoperatoren definieren (siehe [explicit](../../language-reference/keywords/explicit.md) und [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/addition-assignment-operator.md), [-=](../../language-reference/operators/subtraction-assignment-operator.md), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/and-assignment-operator.md), [&#124;=](../../language-reference/operators/or-assignment-operator.md), [^=](../../language-reference/operators/xor-assignment-operator.md), [\<\<=](../../language-reference/operators/left-shift-assignment-operator.md), [>>=](../../language-reference/operators/right-shift-assignment-operator.md)|Zuweisungsoperatoren können nicht explizit überladen werden. Wenn Sie einen binären Operator überladen, wird der zugehörige Zuweisungsoperator jedoch, sofern er vorhanden ist, auch implizit überladen. Wenn `+=` beispielsweise mit `+` ausgewertet wird. Selbiger kann überladen werden.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operator.md), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/dereference-operator.md), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/invocation-operator.md), [as](../../language-reference/keywords/as.md), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/keywords/is.md), [new](../../language-reference/keywords/new.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/keywords/typeof.md)|Diese Operatoren können nicht überladen werden.|

> [!NOTE]
> Die Vergleichsoperatoren müssen, sofern sie überladen sind, paarweise überladen werden. Beim Überladen von `==` muss `!=` demnach ebenfalls überladen werden. Das Gegenteil trifft ebenfalls zu, wenn das Überladen von `!=` eine Überladung von `==` erfordert. Das gleiche gilt für die Vergleichsoperatoren `<`, `>`, `<=` und `>=`.

Informationen zum Überladen eines Operators finden Sie im Keyword-Artikel [Operator](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Anweisungen, Ausdrücke und Operatoren](index.md)
- [Operatoren](operators.md)
- [C#-Operatoren](../../language-reference/operators/index.md)
- [Why are overloaded operators always static in C#? (Warum sind überladene Operatoren in C# immer statisch?)](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/)
