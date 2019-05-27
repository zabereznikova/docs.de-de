---
title: Logische boolesche Operatoren – C#-Referenz
description: Erfahren Sie mehr über C#-Operatoren, die logische Negation, Konjunktion (AND), inklusive und exklusive Disjunktion (OR) mit booleschen Operanden durchführen.
ms.date: 04/08/2019
author: pkulikov
f1_keywords:
- '!_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
- '&&_CSharpKeyword'
- '||_CSharpKeyword'
helpviewer_keywords:
- logical operators [C#]
- short-circuiting operators [C#]
- logical negation operator [C#]
- NOT operator [C#]
- '! operator [C#]'
- AND operator [C#]
- ampersand operator [C#]
- conjunction operator [C#]
- '& operator [C#]'
- exclusive OR operator [C#]
- XOR operator [C#]
- ^ operator [C#]
- OR operator [C#]
- disjunction operator [C#]
- '| operator [C#]'
- conditional AND operator [C#]
- short-circuiting AND operator [C#]
- '&& operator [C#]'
- conditional OR operator [C#]
- short-circuiting OR operator [C#]
- '|| operator [C#]'
ms.openlocfilehash: b666c915506872930b16c1c5890de24e9cbe4f7a
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880580"
---
# <a name="boolean-logical-operators-c-reference"></a>Logische boolesche Operatoren – C#-Referenz

Die folgenden Operatoren führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden durch:

- Unärer [`!` (logische Negation)](#logical-negation-operator-) Operator.
- Binäre [`&` (logisch AND)](#logical-and-operator-), [`|` (logisch OR)](#logical-or-operator-) und [`^` (logisch exklusiv OR)](#logical-exclusive-or-operator-) Operatoren. Diese Operatoren werten immer beide Operanden aus.
- Binäre [ `&&` (bedingt logisch AND)](#conditional-logical-and-operator-) und [ `||` (bedingt logisch OR)](#conditional-logical-or-operator-) Operatoren. Diese Operatoren werten den zweiten Operanden nur dann aus, wenn es notwendig ist.

Für die Operanden der [integralen](../keywords/integral-types-table.md) Typen führen die Operatoren `&`, `|` und `^` bitweise logische Operationen durch. Weitere Informationen finden Sie unter [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md).

## <a name="logical-negation-operator-"></a>Logischer Negationsoperator: !

Der `!`-Operator berechnet die logische Negation des Operanden. Das heißt., er erzeugt `true`, wenn der Operand als `false` ausgewertet wird, und `false`, wenn der Operand als `true` ausgewertet wird:

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Negation)]

## <a name="logical-and-operator-amp"></a>Logischer AND-Operator &amp;

Der `&`-Operator berechnet die logische AND-Operation des Operanden. Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden. Andernfalls ist das Ergebnis `false`.

Der `&`-Operator wertet beide Operanden aus, selbst wenn der erste Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des zweiten Operanden `false` sein muss.

Im folgenden Beispiel ist der zweite Operand des `&`-Operators ein Methodenaufruf, der unabhängig vom Wert des ersten Operanden durchgeführt wird:

[!code-csharp-interactive[logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#And)]

Der [bedingte logische AND-Operator](#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den zweiten Operanden aber nicht aus, wenn der erste Operand `false` ergibt.

Für die Operanden der integralen Typen berechnet der Operator `&` [bitweises logisches UND](bitwise-and-shift-operators.md#logical-and-operator-) für seine Operanden. Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).

## <a name="logical-exclusive-or-operator-"></a>Logischer exklusiver OR-Operator: ^

Die `^`-Operator berechnet das logische exklusive OR, auch als logischer XOR bezeichnet, seiner Operanden. Das Ergebnis von `x ^ y` ist `true`, wenn `x` `true` ergibt und `y` `false`ergibt, oder `x` `false` ergibt und `y` `true` ergibt. Andernfalls ist das Ergebnis `false`. Das heißt, für die `bool`-Operanden berechnet der `^`-Operator das gleiche Ergebnis wie der [Ungleichheitsoperator](equality-operators.md#inequality-operator-) `!=`.

[!code-csharp-interactive[logical exclusive OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Xor)]

Für die Operanden der integralen Typen berechnet der Operator `^` [bitweises logisches exklusives ODER](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) für seine Operanden.

## <a name="logical-or-operator-"></a>Logischer OR-Operator: |

Der `|`-Operator berechnet die logische OR-Operation des Operanden. Das Ergebnis von `x | y` ist `true`, wenn entweder `x` oder `y` `true` ergibt. Andernfalls ist das Ergebnis `false`.

Der `|`-Operator wertet beide Operanden aus, selbst wenn der erste Operand als `true` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des zweiten Operanden `true` sein muss.

Im folgenden Beispiel ist der zweite Operand des `|`-Operators ein Methodenaufruf, der unabhängig vom Wert des ersten Operanden durchgeführt wird:

[!code-csharp-interactive[logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Or)]

Der [bedingte logische OR-Operator](#conditional-logical-or-operator-) `||` berechnet auch die logische OR-Operation der Operanden, wertet den zweiten Operanden aber nicht aus, wenn der erste Operand `true` ergibt.

Für die Operanden der integralen Typen berechnet der Operator `|` [bitweises logisches ODER](bitwise-and-shift-operators.md#logical-or-operator-) für seine Operanden.

## <a name="conditional-logical-and-operator-ampamp"></a>Bedingter logischer AND-Operator &amp;&amp;

Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der Operanden. Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden. Andernfalls ist das Ergebnis `false`. Wenn der erste Operand als `false` ausgewertet wird, wird der zweite Operand nicht ausgewertet.

Im folgenden Beispiel ist der zweite Operand des `&&`-Operators ein Methodenaufruf, der nicht durchgeführt wird, wenn der erste Operand `false` ergibt:

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalAnd)]

Der [logische AND-Operator](#logical-and-operator-) `&` berechnet auch die logische AND-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.

## <a name="conditional-logical-or-operator-"></a>Bedingter logischer OR-Operator ||

Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der Operanden. Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt. Andernfalls ist das Ergebnis `false`. Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet.

Im folgenden Beispiel ist der zweite Operand des `||`-Operators ein Methodenaufruf, der nicht durchgeführt wird, wenn der erste Operand `true` ergibt:

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#ConditionalOr)]

Der [logische OR-Operator](#logical-or-operator-) `|` berechnet auch die logische OR-Operation der Operanden, es werden jedoch immer beide Operanden ausgewertet.

## <a name="nullable-boolean-logical-operators"></a>Logische boolesche Operatoren, die NULL-Werte zulassen

Für die `bool?`-Operanden unterstützen die `&`- und `|`-Operatoren die dreiwertige Logik. Die Semantik dieser Operatoren ist in der folgenden Tabelle definiert:  
  
|w|y|x&y|x&#124;y|  
|----|----|----|----|  
|true|true|true|true|  
|true|False|false|true|  
|true|NULL|NULL|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|NULL|False|NULL|  
|NULL|true|NULL|true|  
|NULL|False|False|NULL|  
|NULL|NULL|NULL|NULL|  

Das Verhalten dieser Operatoren unterscheidet sich vom typischen Operatorverhalten bei Typen, die NULL-Werte zulassen. In der Regel kann ein Operator, der für Operanden eines Werttyps definiert ist, auch mit Operanden des entsprechenden Nullable-Typs verwendet werden. Ein solcher Operator erzeugt `null`, wenn einer seiner Operanden `null` ist. Die `&`- und `|`-Operatoren können jedoch Nicht-NULL-Werte erzeugen, auch wenn einer der Operanden `null` ist. Weitere Informationen zum Operatorverhalten bei Typen, die NULL-Werte zulassen, finden Sie im Abschnitt [Operatoren](../../programming-guide/nullable-types/using-nullable-types.md#operators) des Artikels [Verwenden von Nullable-Typen](../../programming-guide/nullable-types/using-nullable-types.md).

Sie können auch die `!`- und `^`- Operatoren mit den `bool?`-Operanden verwenden, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[lifted negation and xor](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#WithNullableBoolean)]

Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die `bool?`-Operanden.

## <a name="compound-assignment"></a>Verbundzuweisung

Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form

```csharp
x op= y
```

für die folgende Syntax:

```csharp
x = x op y
```

außer dass `x` nur einmal überprüft wird.

Die `&`-, `|`- und `^`-Operatoren unterstützen die Verbundzuweisung, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#CompoundAssignment)]

Die bedingten logischen Operatoren `&&` und `||` unterstützen nicht die Verbundzuweisung.

## <a name="operator-precedence"></a>Operatorrangfolge

In der folgenden Liste sind die logischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:

- Logischer Negationsoperator `!`
- Logischer AND-Operator `&`
- Logischer exklusiver OR-Operator `^`
- Logischer OR-Operator `|`
- Bedingter logischer AND-Operator `&&`
- Bedingter logischer OR-Operator `||`

Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:

[!code-csharp-interactive[operator precedence](~/samples/snippets/csharp/language-reference/operators/LogicalOperators.cs#Precedence)]

Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](index.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann die Operatoren `!`, `&`, `|` und `^` [überladen](../keywords/operator.md). Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen. Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.

Ein benutzerdefinierter Typ kann die bedingten logischen Operatoren `&&` und `||` nicht überladen. Wenn jedoch ein benutzerdefinierter Typ die [„true“ und „false“-Operatoren](../keywords/true-false-operators.md) und den `&`- oder `|`-Operator in einer bestimmten Weise überlädt, kann die `&&`- bzw. `||`-Operation für die Operanden dieses Typs ausgewertet werden. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Logischer Negationsoperator](~/_csharplang/spec/expressions.md#logical-negation-operator)
- [Logical operators (Logische Operatoren)](~/_csharplang/spec/expressions.md#logical-operators)
- [Conditional logical operators (Bedingte logische Operatoren)](~/_csharplang/spec/expressions.md#conditional-logical-operators)
- [Verbundzuweisung](~/_csharplang/spec/expressions.md#compound-assignment)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Bitweise und Schiebeoperatoren](bitwise-and-shift-operators.md)
