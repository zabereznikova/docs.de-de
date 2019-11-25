---
title: 'Operatoren „true“ und „false“: C#-Referenz'
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 780c63e5a8f3f0d82559565b3319fe54507e3d21
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036123"
---
# <a name="true-and-false-operators-c-reference"></a>Operatoren „true“ und „false“ (C#-Referenz)

Der `true`-Operator gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass der Operand definitiv den Wert „true“ hat. Der `false`-Operator gibt den `bool`-Wert `true` zurück, um anzugeben, dass der Operand definitiv den Wert „false“ hat. Es kann nicht garantiert werden, dass sich die Operatoren `true` und `false` gegenseitig ergänzen. Dies bedeutet, dass sowohl der Operator `true` als auch der Operator `false` möglicherweise den `bool`-Wert `false` für den gleichen Operanden zurückgeben. Wenn ein Typ einen der beiden Operatoren definiert, muss er auch den anderen Operator definieren.

> [!TIP]
> Verwenden Sie den Typ `bool?`, wenn Sie die dreiwertige Logik unterstützen müssen (z. B. wenn Sie mit Datenbanken arbeiten, die einen dreiwertigen booleschen Typ unterstützen). C# stellt die `&`- und `|`-Operatoren zur Verfügung, die die dreiwertige Logik mit den `bool?`-Operanden unterstützen. Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](boolean-logical-operators.md).

## <a name="boolean-expressions"></a>Boolesche Ausdrücke

Ein Typ mit dem definierten `true`-Operator kann der Typ des Ergebnisses eines steuernden bedingten Ausdrucks in [if](../keywords/if-else.md)-, [do](../keywords/do.md)-, [while](../keywords/while.md)- und [for](../keywords/for.md)-Anweisungen und im [bedingten Operator `?:`](conditional-operator.md) sein. Weitere Informationen finden Sie im Abschnitt [Boolescher Ausdruck](~/_csharplang/spec/expressions.md#boolean-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="user-defined-conditional-logical-operators"></a>Benutzerdefinierte bedingte logische Operatoren

Wenn ein Typ mit den definierten Operatoren `true` und `false` den [logischen OR-Operator](boolean-logical-operators.md#logical-or-operator-) `|` oder den [logischen AND-Operator](boolean-logical-operators.md#logical-and-operator-) `&` in einer bestimmten Weise [überlädt](operator-overloading.md), kann der [bedingte logische OR-Operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||` bzw. der [bedingte logische AND-Operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` für Operanden dieses Typs ausgewertet werden. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt den Typ, der sowohl `true`- als auch `false`-Operatoren definiert. Außerdem überlädt der Typ den logischen AND-Operator `&` so, dass der Operator `&&` auch für die Operanden dieses Typs ausgewertet werden kann.

[!code-csharp[true and false operators example](~/samples/csharp/language-reference/operators/TrueFalseOperators.cs)]

Beachten Sie das kurzschließende Verhalten des `&&`-Operators. Wenn die `GetFuelLaunchStatus`-Methode `LaunchStatus.Red` zurückgibt, wird der rechte Operand des `&&`-Operators nicht ausgewertet. Der Grund dafür ist, dass `LaunchStatus.Red` definitiv „false“ ist. Dann hängt das Ergebnis des logischen AND-Operators nicht vom Wert des rechten Operanden ab. Die Ausgabe des Beispiels sieht folgendermaßen aus:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [true-Literal](../keywords/true-literal.md)
- [false-Literal](../keywords/false-literal.md)
