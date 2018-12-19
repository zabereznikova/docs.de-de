---
title: Operatoren „true“ und „false“ – C#-Referenz
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: 0a75566fdb6222157ecda12a50fd78e22f92fcb4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245731"
---
# <a name="true-and-false-operators-c-reference"></a>Operatoren „true“ und „false“ (C#-Referenz)

Der `true`-Operator gibt den [bool](bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „true“ hat. Der `false`-Operator gibt den `bool`-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „false“ hat. Es kann nicht garantiert werden, dass sich die Operatoren `true` und `false` gegenseitig ergänzen. Dies bedeutet, dass sowohl der Operator `true` als auch der Operator `false` möglicherweise den `bool`-Wert `false` für den gleichen Operanden zurückgeben. Wenn ein Typ einen der beiden Operatoren definiert, muss er auch den anderen Operator definieren.

Wenn ein Typ mit den definierten Operatoren `true` und `false` den [logischen OR-Operator](../operators/or-operator.md) `|` oder den [logischen AND-Operator](../operators/and-operator.md) `&` in einer bestimmten Weise [überlädt](operator.md), kann der [bedingte logische OR-Operator](../operators/conditional-or-operator.md) `||` bzw. der [bedingte logische AND-Operator](../operators/conditional-and-operator.md) `&&` für Operanden dieses Typs ausgewertet werden. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

Ein Typ mit dem definierten `true`-Operator kann der Typ des Ergebnisses eines steuernden bedingten Ausdrucks in [if](if-else.md)-, [do](do.md)-, [while](while.md)- und [for](for.md)-Anweisungen und im [bedingten Operator `?:`](../operators/conditional-operator.md) sein. Weitere Informationen finden Sie im Abschnitt [Boolescher Ausdruck](~/_csharplang/spec/expressions.md#boolean-expressions) der [C#-Sprachspezifikation](../language-specification/index.md).

> [!TIP]
> Verwenden Sie den Typ `bool?`, wenn Sie die dreiwertige Logik unterstützen müssen, z.B. wenn Sie mit Datenbanken arbeiten, die einen dreiwertigen Logiktyp unterstützen. Weitere Informationen finden Sie im Abschnitt [Der „bool?“-Typ](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) im Artikel [Verwenden von Nullable-Typen](../../programming-guide/nullable-types/using-nullable-types.md).

Das folgende Beispiel zeigt den Typ, der sowohl `true`- als auch `false`-Operatoren definiert. Außerdem überlädt er den logischen AND-Operator `&` so, dass der Operator `&&` auch für die Operanden dieses Typs ausgewertet werden kann.

[!code-csharp-interactive[true and false operators example](~/samples/snippets/csharp/keywords/TrueFalseOperatorsExample.cs)]

Beachten Sie das kurzschließende Verhalten des `&&`-Operators. Wenn die `GetFuelLaunchStatus`-Methode `LaunchStatus.Red` zurückgibt, wird der zweite Operand des `&&`-Operators nicht ausgewertet. Der Grund dafür ist, dass `LaunchStatus.Red` definitiv „false“ ist. Dann hängt das Ergebnis des logischen AND-Operators nicht vom Wert des zweiten Operanden ab. Die Ausgabe des Beispiels sieht folgendermaßen aus:

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [C#-Operatoren](../operators/index.md)
- [`true` Literal](true-literal.md)
- [`false` Literal](false-literal.md)