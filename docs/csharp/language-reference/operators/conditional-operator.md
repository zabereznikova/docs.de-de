---
title: '?: Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: a40dd4addfaf8a505cf334876192f0b2ccf66a09
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452397"
---
# <a name="-operator-c-reference"></a>?: Operator (C#-Referenz)

Der bedingte Operator `?:`, häufig als ternärer bedingter Operator bekannt, wertet einen booleschen Ausdruck aus und gibt das Ergebnis der Auswertung von einem oder zwei Ausdrücken zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt. Beginnend mit C# 7.2 gibt der [bedingte Ref-Ausdruck](#conditional-ref-expression) den Verweis auf das Ergebnis eines der beiden Ausdrücke zurück.

Die Syntax für den bedingten Operator lautet:

```csharp
condition ? consequent : alternative
```

Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden. Wenn `condition` `true` ergibt, wird der `consequent`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Wenn `condition` `false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Nur `consequent` oder `alternative` wird ausgewertet.

Der Typ von `consequent` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.

Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form

```csharp
a ? b : c ? d : e
```

wird als ausgewertet,

```csharp
a ? b : (c ? d : e)
```

Eine Gedächtnisstütze für die Auswertung des Operators ist die folgende Frage:

```text
is this condition true ? yes : no
```

Dabei fungiert das ? im Operatorausdruck als Fragezeichen für die vorherige Anweisung und die daraus folgende Handlung als logische Antwort auf diese Frage.

Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:

[!code-csharp[non ref conditional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Bedingter ref-Ausdruck

Beginnend mit C# 7.2 können Sie mit dem bedingten ref-Ausdruck den Verweis auf das Ergebnis eines der beiden Ausdrücke zurückgeben. Sie können diesen Verweis einer [lokalen Ref-Variablen](../keywords/ref.md#ref-locals) oder [schreibgeschützten lokalen Ref-Variablen](../keywords/ref.md#ref-readonly-locals) zuweisen bzw. als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder [`ref`-Methodenparameter](../keywords/ref.md#passing-an-argument-by-reference) verwenden.

Die Syntax für den bedingten ref-Ausdruck lautet:

```csharp
condition ? ref consequent : ref alternative
```

Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequent` oder `alternative`.

Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequent` und `alternative` identisch sein.

Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](../../../../_csharplang/proposals/csharp-7.2/conditional-ref.md).

## <a name="conditional-operator-and-an-ifelse-statement"></a>Bedingter Operator und eine `if..else`-Anweisung

Die Verwendung des bedingten Operators über einer [if-else](../keywords/if-else.md)-Anweisung könnte in Fällen, in denen Sie einen Wert bedingt berechnen müssen, präziseren Code zur Folge haben. Das folgende Beispiel zeigt zwei Möglichkeiten, eine ganze Zahl als negativ oder nicht negativ zu klassifizieren:

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Der bedingte Operator kann nicht überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Bedingter Operator](~/_csharplang/spec/expressions.md#conditional-operator) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [if-else-Anweisung](../keywords/if-else.md)
- [?.- und ?[]-Operatoren](member-access-operators.md#null-conditional-operators--and-)
- [?? Operator](null-coalescing-operator.md)
- [ref (C#-Referenz)](../keywords/ref.md)
