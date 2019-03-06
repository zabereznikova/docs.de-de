---
title: '* -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977343"
---
# <a name="-operator-c-reference"></a>*-Operator (C#-Referenz)

Der Operator `*` wird in zwei Formen unterstützt: als unärer Zeigerdereferenzierungsoperator oder als binärer Multiplikationsoperator.

## <a name="pointer-indirection-operator"></a>Zeigerdereferenzierungsoperator

Verwenden Sie den unären `*`-Operator, um die Variable zu erhalten, auf die ein Operand vom Typ „Zeiger“ verweist. Weitere Informationen finden Sie unter [Gewusst wie: Abrufen des Werts einer Zeigervariablen](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).

Der Zeigerdereferenzierungsoperator `*` erfordert einen [unsicheren](../keywords/unsafe.md) Kontext.

## <a name="multiplication-operator"></a>Multiplikationsoperator

Für numerische Typen berechnet der `*`-Operator das Produkt seiner Operanden:

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können einen binären `*`-Operator [überladen](../keywords/operator.md). Wenn ein binärer `*`-Operator überladen ist, wird der [Multiplikationszuweisungsoperator](multiplication-assignment-operator.md) `*=`auch implizit überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [C#-Sprachspezifikation](../language-specification/index.md) in den Abschnitten [Zeigerdereferenzierung](~/_csharplang/spec/unsafe-code.md#pointer-indirection) und [Multiplikationsoperator](~/_csharplang/spec/expressions.md#multiplication-operator).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)