---
description: 'Operator „?:“: C#-Referenz'
title: 'Operator „?:“: C#-Referenz'
ms.date: 09/17/2020
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: b6add045983619169bed0cd9f32eb27dba0a0338
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738878"
---
# <a name="-operator-c-reference"></a>Operator „?“ (C#-Referenz)

Der bedingte Operator `?:`, der auch als ternärer bedingter Operator bekannt ist, wertet einen booleschen Ausdruck aus und gibt das Ergebnis für einen der zwei Ausdrücke zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt.

Die Syntax für den bedingten Operator lautet:

```csharp
condition ? consequent : alternative
```

Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden. Wenn `condition``true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Wenn `condition``false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Nur `consequent` oder `alternative` wird ausgewertet.

Ab C# 9.0 weisen bedingte Ausdrücke das Typ des Ziels auf. Wenn der Zieltyp eines bedingten Ausdrucks also bekannt ist, müssen die Typen von `consequent` und `alternative` implizit in den Zieltyp konvertierbar sein, wie im folgenden Beispiel gezeigt wird:

[!code-csharp[target-typed conditional](snippets/shared/ConditionalOperator.cs#TargetTyped)]

Wenn der Zieltyp eines bedingten Ausdrucks nicht bekannt ist, z. B. wenn Sie das [`var`](../keywords/var.md)-Schlüsselwort nutzen oder in C# 8.0 oder älteren Versionen, muss der Typ von `consequent` und `alternative` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in den anderen geben:

[!code-csharp[not target-typed conditional](snippets/shared/ConditionalOperator.cs#NotTargetTyped)]

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

[!code-csharp-interactive[non ref conditional](snippets/shared/ConditionalOperator.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Bedingter ref-Ausdruck

Ab C# 7.2 kann eine lokale [ref](../keywords/ref.md#ref-locals)-Variable oder eine schreibgeschützte lokale [ref](../keywords/ref.md#ref-readonly-locals)-Variable mit dem bedingten ref-Ausdruck bedingt zugewiesen werden. Sie können einen bedingten ref-Ausdruck auch als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder als [`ref`-Methodenargument](../keywords/ref.md#passing-an-argument-by-reference) verwenden.

Die Syntax für den bedingten ref-Ausdruck lautet folgendermaßen:

```csharp
condition ? ref consequent : ref alternative
```

Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.

Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein. Bedingte ref-Ausdrücke weisen nicht den Typ des Ziels auf.

Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:

[!code-csharp-interactive[conditional ref](snippets/shared/ConditionalOperator.cs#ConditionalRef)]

## <a name="conditional-operator-and-an-ifelse-statement"></a>Bedingter Operator und eine `if..else`-Anweisung

Die Verwendung des bedingten Operators anstelle einer [if-else](../keywords/if-else.md)-Anweisung führt in Fällen, in denen Sie einen Wert bedingt berechnen müssen, möglicherweise zu präziserem Code. Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:

[!code-csharp[conditional and if-else](snippets/shared/ConditionalOperator.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann den bedingten Operator nicht überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zu in C# 7.2 und höher eingeführten Features finden Sie in den folgenden Featurevorschlägen:

- [Bedingter ref-Ausdruck (C# 7.2)](~/_csharplang/proposals/csharp-7.2/conditional-ref.md)
- [Bedingter Ausdruck mit Zieltyp (C# 9.0)](~/_csharplang/proposals/csharp-9.0/target-typed-conditional-expression.md)

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [if-else-Anweisung](../keywords/if-else.md)
- [?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)
- [??- und ??=-Operatoren](null-coalescing-operator.md)
- [ref (C#-Referenz)](../keywords/ref.md)
