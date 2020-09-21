---
title: 'Operatorüberladung: C#-Referenz'
description: Erfahren Sie, welche C#-Operatoren überladen werden können und wie Sie dabei vorgehen sollten.
ms.date: 07/05/2019
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
- operator overloading [C#]
ms.openlocfilehash: 65f417c06886c32da8057ae612043b95c31a31bd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536417"
---
# <a name="operator-overloading-c-reference"></a>Operatorüberladung (C#-Referenz)

Ein benutzerdefinierter Typ kann einen vordefinierten C#-Operator überladen. Das bedeutet, dass ein Typ die benutzerdefinierte Implementierung eines Vorgangs bereitstellen kann, wenn mindestens einer der beiden Operanden vom selben Typ ist. Im Abschnitt [Überladbare Operatoren](#overloadable-operators) werden die C#-Operatoren angegeben, die überladen werden können.

Verwenden Sie das Schlüsselwort `operator`, um einen Operator zu deklarieren. Jede Operatordeklaration muss mit den folgenden Regeln konform sein:

- Sie enthält sowohl einen `public`- als auch einen `static`-Modifizierer.
- Ein unärer Operator verfügt über einen Eingabeparameter. Ein binärer Operator verfügt über zwei Eingabeparameter. Auf jeden Fall muss mindestens ein Parameter vom Typ `T` oder `T?` sein, wobei `T` der Typ ist, der die Operatordeklaration enthält.

Das folgende Beispiel definiert eine vereinfachte Struktur für die Darstellung einer rationalen Zahl. Die Struktur überlädt einige der [arithmetischen Operatoren](arithmetic-operators.md):

[!code-csharp[fraction example](snippets/shared/OperatorOverloading.cs)]

Sie könnten das vorherige Beispiel erweitern, indem Sie eine [implizite Konvertierung](user-defined-conversion-operators.md) von `int` nach `Fraction` definieren. Dann würden überladene Operatoren Argumente dieser beiden Typen unterstützen. Das bedeutet, dass es dann möglich wäre, eine ganze Zahl und einen Bruch zu addieren und als Ergebnis einen Bruch zu erhalten.

Verwenden Sie zudem das Kennwort `operator`, um eine benutzerdefinierte Konvertierung zu definieren. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).

## <a name="overloadable-operators"></a>Überladbare Operatoren

Die folgende Tabelle enthält Informationen zur Überladbarkeit von C#-Operatoren:

| Operatoren | Überladbarkeit |
| --------- | --------------- |
|[+x](arithmetic-operators.md#unary-plus-and-minus-operators), [-x](arithmetic-operators.md#unary-plus-and-minus-operators), [!x](boolean-logical-operators.md#logical-negation-operator-), [~x](bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](arithmetic-operators.md#increment-operator-), [--](arithmetic-operators.md#decrement-operator---), [true](true-false-operators.md), [false](true-false-operators.md)|Diese unären Operatoren können überladen werden.|
|[x + y](addition-operator.md), [x - y](subtraction-operator.md), [x \* y](arithmetic-operators.md#multiplication-operator-), [x / y](arithmetic-operators.md#division-operator-), [x % y](arithmetic-operators.md#remainder-operator-), [x & y](boolean-logical-operators.md#logical-and-operator-), [x &#124; y](boolean-logical-operators.md#logical-or-operator-), [x ^ y](boolean-logical-operators.md#logical-exclusive-or-operator-), [x \<\< y](bitwise-and-shift-operators.md#left-shift-operator-), [x >> y](bitwise-and-shift-operators.md#right-shift-operator-), [x == y](equality-operators.md#equality-operator-), [x != y](equality-operators.md#inequality-operator-), [x \< y](comparison-operators.md#less-than-operator-), [x > y](comparison-operators.md#greater-than-operator-), [x \<= y](comparison-operators.md#less-than-or-equal-operator-), [x >= y](comparison-operators.md#greater-than-or-equal-operator-)|Diese binären Operatoren können überladen werden. Manche Operatoren müssen paarweise überladen werden. Weitere Informationen dazu finden Sie im Hinweisfeld unter dieser Tabelle.|
|[x && y](boolean-logical-operators.md#conditional-logical-and-operator-), [x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-)|Bedingte logische Operatoren können nicht überladen werden. Wenn jedoch ein Typ mit den überladenen Operatoren [`true` und `false` ebenfalls den Operator](true-false-operators.md)`&` oder <code>&#124;</code> auf eine bestimmte Weise überlädt, kann jeweils entweder der Operator `&&` oder der Operator <code>&#124;&#124;</code> für die Operanden dieses Typs ausgewertet werden. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).|
|[a&#91;i&#93;](member-access-operators.md#indexer-operator-), [`a?[i]`](member-access-operators.md#null-conditional-operators--and-)|Der Elementzugriff wird nicht als überladbarer Operator betrachtet. Sie können aber einen [Indexer](../../programming-guide/indexers/index.md) definieren.|
|[(T)x](type-testing-and-cast.md#cast-expression)|Der Cast-Operator kann nicht überladen werden, jedoch können Sie benutzerdefinierte Typkonvertierungen definieren, die von einem Cast-Ausdruck durchgeführt werden können. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).|
|[+=](arithmetic-operators.md#compound-assignment), [-=](arithmetic-operators.md#compound-assignment), [\*=](arithmetic-operators.md#compound-assignment), [/=](arithmetic-operators.md#compound-assignment), [%=](arithmetic-operators.md#compound-assignment), [&=](boolean-logical-operators.md#compound-assignment), [&#124;=](boolean-logical-operators.md#compound-assignment), [^=](boolean-logical-operators.md#compound-assignment), [\<\<=](bitwise-and-shift-operators.md#compound-assignment), [>>=](bitwise-and-shift-operators.md#compound-assignment)|Zusammengesetzte Zuweisungsoperatoren können nicht explizit überladen werden. Wenn Sie einen binären Operator überladen, wird der zugehörige zusammengesetzte Zuweisungsoperator jedoch, sofern er vorhanden ist, auch implizit überladen. Wenn `+=` beispielsweise mit `+` ausgewertet wird. Selbiger kann überladen werden.|
|[^x](member-access-operators.md#index-from-end-operator-), [x = y](assignment-operator.md), [x.y](member-access-operators.md#member-access-expression-), [`x?.y`](member-access-operators.md#null-conditional-operators--and-), [c ? t : f](conditional-operator.md), [x ?? y](null-coalescing-operator.md), [x ??= y](null-coalescing-operator.md), [x..y](member-access-operators.md#range-operator-), [x->y](pointer-related-operators.md#pointer-member-access-operator--), [=>](lambda-operator.md), [f(x)](member-access-operators.md#invocation-expression-), [as](type-testing-and-cast.md#as-operator), [await](await.md), [checked](../keywords/checked.md), [unchecked](../keywords/unchecked.md), [default](default.md), [delegate](delegate-operator.md), [is](type-testing-and-cast.md#is-operator), [nameof](nameof.md), [new](new-operator.md), [sizeof](sizeof.md), [stackalloc](stackalloc.md), [switch](switch-expression.md), [typeof](type-testing-and-cast.md#typeof-operator)|Diese Operatoren können nicht überladen werden.|

> [!NOTE]
> Die Vergleichsoperatoren müssen paarweise überladen werden. Das bedeutet: Wenn ein Operator überladen wird, der einem Paar angehört, muss der andere Operator ebenfalls überladen werden. Dies kann für die folgenden Paare zutreffen:
>
> - Die Operatoren `==` und `!=`
> - Die Operatoren `<` und `>`
> - Die Operatoren `<=` und `>=`

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Operatorüberladung](~/_csharplang/spec/expressions.md#operator-overloading)
- [Operatoren](~/_csharplang/spec/classes.md#operators)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md)
- [Entwurfsrichtlinien: Operatorüberladungen](../../../standard/design-guidelines/operator-overloads.md)
- [Entwurfsrichtlinien: Gleichheitsoperatoren](../../../standard/design-guidelines/equality-operators.md)
- [Why are overloaded operators always static in C#? (Warum sind überladene Operatoren in C# immer statisch?)](/archive/blogs/ericlippert/why-are-overloaded-operators-always-static-in-c)
