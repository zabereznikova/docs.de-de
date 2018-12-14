---
title: 'Operator ?: (C#-Referenz)'
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: cc9bde1d60a3272e2f24cfc05761171a31029c75
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2018
ms.locfileid: "50980621"
---
# <a name="-operator-c-reference"></a>Operator ?: (C#-Referenz)

Der bedingte Operator `?:`, häufig als ternärer bedingter Operator bekannt, wertet einen booleschen Ausdruck aus und gibt das Ergebnis der Auswertung von einem oder zwei Ausdrücken zurück, abhängig davon, ob der boolesche Ausdruck `true` oder `false` ergibt. Beginnend mit C# 7.2 gibt der [bedingte Ref-Ausdruck](#conditional-ref-expression) den Verweis auf das Ergebnis eines der beiden Ausdrücke zurück.

Die Syntax für den bedingten Operator lautet:

```csharp
condition ? consequence : alternative
```

Der `condition`-Ausdruck muss als `true` oder `false` ausgewertet werden. Wenn `condition` `true` ergibt, wird der `consequence`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Wenn `condition` `false` ergibt, wird der `alternative`-Ausdruck ausgewertet, und das Ergebnis ist das Ergebnis des Vorgangs. Nur `consequence` oder `alternative` wird ausgewertet.

Der Typ von `consequence` und `alternative` muss identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.

Der bedingte Operator ist rechtsassoziativ, d.h. ein Ausdruck der Form

```csharp
a ? b : c ? d : e
```

wird als ausgewertet,

```csharp
a ? b : (c ? d : e)
```

Im folgenden Beispiel wird die Verwendung des bedingten Operators veranschaulicht:

[!code-csharp[non ref condtional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Bedingter ref-Ausdruck

Beginnend mit C# 7.2 können Sie mit dem bedingten ref-Ausdruck den Verweis auf das Ergebnis eines der beiden Ausdrücke zurückgeben. Sie können diesen Verweis einer [lokalen Ref-Variablen](../keywords/ref.md#ref-locals) oder [schreibgeschützten lokalen Ref-Variablen](../keywords/ref.md#ref-readonly-locals) zuweisen bzw. als [Verweisrückgabewert](../keywords/ref.md#reference-return-values) oder [`ref`-Methodenparameter](../keywords/ref.md#passing-an-argument-by-reference) verwenden.

Die Syntax für den bedingten ref-Ausdruck lautet:

```csharp
condition ? ref consequence : ref alternative
```

Wie der ursprüngliche bedingte Operator wertet der bedingte ref-Ausdruck nur einen von zwei Ausdrücken aus: entweder `consequence` oder `alternative`.

Im Fall des bedingten ref-Ausdrucks muss der Typ von `consequence` und `alternative` identisch sein.

Im folgenden Beispiel wird die Verwendung des bedingten ref-Ausdrucks veranschaulicht:

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

Weitere Informationen finden Sie unter [Hinweis zum Featurevorschlag](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md).

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
- [?.- und ?[]-Operatoren](null-conditional-operators.md)
- [?? Operator](null-coalescing-operator.md)
- [ref (C#-Referenz)](../keywords/ref.md)
