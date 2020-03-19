---
title: 'Operator „?:“: C#-Referenz'
ms.date: 03/06/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 1a17ba092d4228ba909c8774a2f7e15c2c50cfdc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398214"
---
# <a name="-operator-c-reference"></a>Operator „?“ (C#-Referenz)

Der bedingte Operator `?:`, der auch als ternärer bedingter Operator bekannt ist, wertet einen booleschen Ausdruck aus und gibt das Ergebnis für einen der zwei Ausdrücke zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.

Die Syntax für den bedingten Operator lautet:

```csharp
condition ? consequent : alternative
```

Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden. Wenn `condition``true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Wenn `condition``false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Nur `consequent` oder `alternative` wird ausgewertet.

Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.

Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form

```csharp
a ? b : c ? d : e
```

wird als ausgewertet,

```csharp
a ? b : (c ? d : e)
```

> [!TIP]
> Sie können sich anhand der folgenden Gedächtnisstütze merken, wie der bedingte Operator ausgewertet wird:
>
> ```text
> is this condition true ? yes : no
> ```

Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:

[!code-csharp-interactive[non ref conditional](snippets/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Bedingter ref-Ausdruck

Ab C# 7.2 kann eine lokale [ref](../keywords/ref.md#ref-locals)-Variable oder eine schreibgeschützte lokale [ref](../keywords/ref.md#ref-readonly-locals)-Variable mit dem bedingten ref-Ausdruck bedingt zugewiesen werden. Sie können den bedingten ref-Ausdruck auch als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder als [`ref`-Methodenargument](../keywords/ref.md#passing-an-argument-by-reference) verwenden.

Die Syntax für den bedingten ref-Ausdruck lautet:

```csharp
condition ? ref consequent : ref alternative
```

Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.

Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.

Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:

[!code-csharp-interactive[conditional ref](snippets/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Bedingter Operator und eine `if..else`-Anweisung

Die Verwendung des bedingten Operators anstelle einer [if-else](../keywords/if-else.md)-Anweisung führt in Fällen, in denen Sie einen Wert bedingt berechnen müssen, möglicherweise zu präziserem Code. Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:

[!code-csharp[conditional and if-else](snippets/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den bedingten Operator nicht überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zum bedingten REF-Ausdruck finden Sie unter [Hinweis zum Featurevorschlag](~/_csharplang/proposals/csharp-7.2/conditional-ref.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [if-else-Anweisung](../keywords/if-else.md)
- [?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)
- [??- und ??=-Operatoren](null-coalescing-operator.md)
- [ref (C#-Referenz)](../keywords/ref.md)
