---
title: 'Operator ?: (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 3e45ff6eaaefa5829c3ed9415abe1a12b7a1d069
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980621"
---
# <a name="-operator-c-reference"></a>Operator ?: (C#-Referenz)

Der bedingte Operator (`?:`), gemeinhin als ternärer bedingter Operator bekannt, gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück. Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.  

```csharp
condition ? first_expression : second_expression;  
```

Beginnend mit C# 7.2 können `first_expression` und `second_expression` [`ref`-Ausdrücke sein](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md):

```csharp
ref condition ? ref first_expression : ref second_expression;  
```

Das Ergebnis kann einer `ref`- oder `ref readonly`-Variablen oder einer Variable mit keinem der beiden Modifizierer zugewiesen werden.

## <a name="remarks"></a>Hinweise

`condition` muss mit `true` oder `false` ausgewertet werden. Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet. Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet. Nur einer der beiden Ausdrücke wird ausgewertet. Dies ist besonders wichtig für Ausdrücke, deren Ergebnis ein `ref` ist, da Folgendes gilt:

```csharp
ref (storage != null) ? ref storage[3] : ref defaultValue;
```

Der Verweis auf `storage` wird nicht ausgewertet, wenn `storage` null ist.

Wenn das Ergebnis ein Wert ist, muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein. Wenn das Ergebnis ein `ref` ist, muss der Typ von `first_expression` und `second_expression` identisch sein.

Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`-Konstruktion benötigen. Im folgenden Code wird z. B. zuerst eine `if`-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.

```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```

Der bedingte Operator ist rechtsassoziativ. Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.  
  
Der bedingte Operator kann nicht überladen werden.
  
## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt den bedingten Operator, dessen Ergebnis ein Wert ist:

[!code-csharp[csRefOperators?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

Die folgende Alternative zeigt den bedingten Operator, dessen Ergebnis ein Verweis ist:

[!code-csharp[csRefOperatorsRef?:](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [?.- und ?[]-Operatoren](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [?? Operator](../../../csharp/language-reference/operators/null-coalescing-operator.md)
