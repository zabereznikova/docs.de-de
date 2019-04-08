---
title: + +-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 0f04ba837f9c03107acd0b2174cbd07c14a8c213
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504469"
---
# <a name="-operator-c-reference"></a>Operator + (C#-Referenz)

Der Operator `+` wird in zwei Formen unterstützt: als unärer Plusoperator oder als binärer Additionsoperator.

## <a name="unary-plus-operator"></a>Unärer Plus-Operator

Der unäre `+`-Operator gibt den Wert seines Operanden zurück. Er wird von allen numerischen Typen unterstützt.

## <a name="numeric-addition"></a>Numerische Addition

Für numerische Typen berechnet der `+`-Operator die Summe der Operanden:

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

Weitere Informationen zu arithmetischen Operatoren finden Sie unter [Arithmetische Operatoren](arithmetic-operators.md).

## <a name="string-concatenation"></a>Zeichenfolgenverkettung

Wenn ein Operand oder beide Operanden vom Typ [String](../keywords/string.md) sind, verkettet der `+`-Operator die Zeichenfolgendarstellungen der Operanden:

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

Ab C# 6 bietet die [Zeichenfolgeninterpolation](../tokens/interpolated.md) eine benutzerfreundliche Option zum Formatieren von Zeichenfolgen:

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Kombinieren von Delegaten

Für [Delegattypen](../keywords/delegate.md) gibt der Operator `+` eine neue Delegatinstanz zurück, die beim Aufruf den ersten Operanden und dann den zweiten Operanden aufruft. Wenn einer der Operanden `null` lautet, gibt der `+`-Operator den Wert eines anderen Operanden zurück (der ggf. ebenfalls `null` ist). Das folgende Beispiel zeigt, wie Delegaten mit dem `+`-Operator kombiniert werden können:

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können die unären und binären `+`-Operatoren [überladen](../keywords/operator.md). Wenn ein binärer `+`-Operator überladen ist, wird der [Additionszuweisungsoperator](addition-assignment-operator.md) `+=`auch implizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [C#-Sprachspezifikation](../language-specification/index.md) in den Abschnitten [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator) und [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Zeichenfolgeninterpolation](../tokens/interpolated.md)
- [Vorgehensweise: Verketten von mehreren Zeichenfolgen](../../how-to/concatenate-multiple-strings.md)
- [Delegaten](../../programming-guide/delegates/index.md)
- [Checked und unchecked](../keywords/checked-and-unchecked.md)
