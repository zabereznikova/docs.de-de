---
title: '&amp;-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310043"
---
# <a name="amp-operator-c-reference"></a>&amp;-Operator (C#-Referenz)

Der Operator `&` wird in zwei Formen unterstützt: als unärer address-of-Operator oder als binärer logischer Operator.

## <a name="unary-address-of-operator"></a>Unärer address-of-Operator

Der unäre `&`-Operator gibt die Adresse seines Operanden zurück. Weitere Informationen finden Sie unter [Gewusst wie: Abrufen der Adresse einer Variablen](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).

Der address-of-Operator `&` erfordert [unsicheren](../keywords/unsafe.md)-Kontext.

## <a name="integer-logical-bitwise-and-operator"></a>Ganzzahliger bitweiser logischer AND-Operator

Für ganzzahlige Datentypen berechnet der `&`-Operator die bitweise logische AND-Operation der Operanden:

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> Im Beispiel oben werden die [in C# 7.0 eingeführten](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) und [in C# 7.2 erweiterten](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals) binären Literale verwendet.

Da die Operationen für ganzzahlige Datentypen im Allgemeinen für Enumerationstypen zulässig sind, unterstützt der `&`-Operator auch [enum](../keywords/enum.md)-Operanden.

## <a name="boolean-logical-and-operator"></a>Boolescher logischer AND-Operator

Für [bool](../keywords/bool.md)-Operanden berechnet der `&`-Operator die logische AND-Operation der Operanden. Das Ergebnis von `x & y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden. Andernfalls ist das Ergebnis `false`.

Der `&`-Operator wertet beide Operanden aus, selbst wenn der erste Operand als `false` ausgewertet wird, sodass das Ergebnis unabhängig vom Wert des zweiten Operanden `false` sein muss. Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

Der [bedingte AND-Operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` berechnet auch die logische AND-Operation der Operanden, wertet den zweiten Operanden aber nicht aus, wenn der erste Operand `false` ergibt.

Für Operanden, die NULL-Werte zulassen, ist das Verhalten des `&`-Operators konsistent mit der dreiwertigen Logik von SQL. Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](boolean-logical-operators.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den binären `&`-Operator [überladen](../keywords/operator.md). Wenn ein binärer `&`-Operator überladen ist, wird der [AND-Zuweisungsoperator](and-assignment-operator.md) `&=` auch implizit überladen.

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

Weitere Informationen finden Sie in den Abschnitten [Der address-of-Operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) und [Logische Operatoren](~/_csharplang/spec/expressions.md#logical-operators) der [C#-Programmiersprachenspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Logische boolesche Operatoren](boolean-logical-operators.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [|-Operator](or-operator.md)
- [^-Operator](xor-operator.md)
- [~-Operator](bitwise-complement-operator.md)
