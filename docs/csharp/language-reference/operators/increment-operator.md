---
title: Operator ++ (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030469"
---
# <a name="-operator-c-reference"></a>Operator ++ (C#-Referenz)

Der unäre Inkrementoperator (`++`) erhöht seinen Operanden um 1. Er wird in zwei Formen unterstützt: der Postfix-Inkrementoperator `x++` und der Präfix-Inkrementoperator `++x`.

## <a name="postfix-increment-operator"></a>Postfix-Operator für Inkrement

Das Ergebnis von `x++` ist der Wert von `x`  *vor* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a>Präfixinkrement-Operator

Das Ergebnis von `++x` ist der Wert von `x`  *nach* dem Vorgang, wie das folgende Beispiel zeigt:

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a>Hinweise

Der Inkrementoperator ist für alle [integralen Datentypen](../keywords/integral-types-table.md) (einschließlich [char](../keywords/char.md)-Typ), [Gleitkommatypen](../keywords/floating-point-types-table.md) und alle [Enumerationstypen](../keywords/enum.md) vordefiniert.

Ein Operand des Inkrementoperators muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexzugriff](../../../csharp/programming-guide/indexers/index.md) sein.

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Benutzerdefinierte Typen können den Operator `++` [überladen](../keywords/operator.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den Abschnitten [Postfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) und [Präfix-Inkrement- und Dekrementoperatoren](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) der [C#-Sprachspezifikation](../language-specification/index.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- [-- Operator](decrement-operator.md)
- [Gewusst wie: Inkrementieren und Dekrementieren von Zeigern](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
