---
title: Operator % (C#-Referenz)
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: 9cd2f7ad3856feb34667686979c942ecb21887c2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266695"
---
# <a name="-operator-c-reference"></a>Operator % (C#-Referenz)

Der Restoperator `%` berechnet den Rest nach der Division seines ersten Operanden durch den zweiten Operanden. Benutzerdefinierte Typen können den Operator `%` [überladen](../keywords/operator.md). Wenn `%` überladen ist, ist der [Restzuweisungsoperator](remainder-assignment-operator.md) `%=` ebenfalls implizit überladen.

Alle numerischen Typen unterstützen den Restoperator.

## <a name="integer-remainder"></a>Ganzzahliger Rest
  
Für ganzzahlige Operanden entspricht das Ergebnis von `a % b` dem von `a - (a / b) * b` erzeugten Wert. Das Vorzeichen des Rests, der ungleich 0 (null) ist, ist wie im folgenden Beispiel gezeigt identisch mit dem des ersten Operanden:

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a>Gleitkommarest

Für die Operanden [float](../keywords/float.md) und [double](../keywords/double.md) entspricht das Ergebnis von `x % y` für die begrenzten Werte `x` und `y` dem Wert `z`, sodass:

- das Vorzeichen von `z` dem Vorzeichen von `x` entspricht, sofern der Wert nicht 0 (null) ist.
- der absolute Wert von `z` dem von `|x| - n * |y|` erzeugten Wert entspricht, wobei `n` der größten möglichen Ganzzahl entspricht, die kleiner oder gleich `|x| / |y|` ist. Dementsprechend sind `|x|` und `|y|` jeweils die absoluten Werte von `x` und `y`.

Weitere Informationen zum Verhalten des `%`-Operators im Fall von nicht begrenzten Operanden finden Sie im Abschnitt [Restoperator](/dotnet/csharp/language-reference/language-specification/expressions#remainder-operator) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/index).

> [!NOTE]
> Diese Methode zum Berechnen des Rests ist analog zu der Methode, die für ganzzahlige Operanden verwendet wird, unterscheidet sich jedoch von der Norm IEEE 754. Wenn Sie den Restvorgang benötigen, der der Norm IEEE 754 entspricht, verwenden Sie die Methode <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.

Im folgenden Beispiel wird das Verhalten des Restoperators für die Operanden `float` und `double` veranschaulicht.

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

Beachten Sie die Rundungsfehler, die im Zusammenhang mit den Gleitkommatypen stehen.

Der Restoperator `%` entspricht für die [decimal](../keywords/decimal.md)-Operanden dem [Restoperator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) vom Typ <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
