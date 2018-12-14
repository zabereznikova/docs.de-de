---
title: Operator -- (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 0858321d6fe192a55bc548f169c558542238a981
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153335"
---
# <a name="---operator-c-reference"></a>Operator -- (C#-Referenz)

Der unäre Dekrementoperator `--` verringert seinen Operanden um 1. Er wird in zwei Formen unterstützt: der Postfix-Dekrementoperator `x--` und der Präfix-Dekrementoperator `--x`.

## <a name="postfix-decrement-operator"></a>Postfix-Operator für Dekrement

Das Ergebnis von `x--` ist der Wert von `x`  *vor* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a>Präfix-Dekrementoperator

Das Ergebnis von `--x` ist der Wert von `x`  *nach* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a>Hinweise

Der Dekrementoperator ist für alle [integralen Datentypen](../keywords/integral-types-table.md) (einschließlich [char](../keywords/char.md)-Typ), [Gleitkommatypen](../keywords/floating-point-types-table.md), und alle [Enumerationstypen](../keywords/enum.md) vordefiniert.

Ein Operand des Dekrementoperators muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexzugriff](../../../csharp/programming-guide/indexers/index.md) sein.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `--` [überladen](../keywords/operator.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Postfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) und [Präfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [++-Operator](increment-operator.md)
- [Gewusst wie: Inkrementieren und Dekrementieren von Zeigern](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
