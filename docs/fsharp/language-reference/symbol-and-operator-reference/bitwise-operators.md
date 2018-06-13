---
title: Bitweise Operatoren (F#)
description: Erfahren Sie, bis die bitweisen Operatoren, die in der Programmiersprache f# verfügbar sind.
ms.date: 05/16/2016
ms.openlocfilehash: bc653ae7ff6dd6bc2c269aaba344f073df1fb708
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565326"
---
# <a name="bitwise-operators"></a>Bitweise Operatoren

In diesem Thema wird beschrieben, bitweise Operatoren, die in der Programmiersprache f# verfügbar sind.

## <a name="summary-of-bitwise-operators"></a>Zusammenfassung der bitweise Operatoren
Die folgende Tabelle beschreibt die bitweisen Operatoren, die für nicht geschachtelte ganzzahlige Typen in der Programmiersprache f# unterstützt werden.

|Operator|Hinweise|
|--------|-----|
|`&&&`|Bitweiser AND-Operator. Bits im Resultset haben den Wert 1, wenn die entsprechenden Bits in beide Quelloperanden den Wert 1 haben.|
|<code>&#124;&#124;&#124;</code>|Bitweiser OR-Operator. Bits im Resultset den Wert 1 aufweisen, wenn entweder der entsprechenden Bits in der Quelle Operanden 1 sind.|
|`^^^`|Bitweiser exklusiver OR-Operator. Bits im Resultset aufweisen den Wert 1, wenn Bits in den Quelloperanden ungleiche Werte aufweisen.|
|`~~~`|Bitweise Negation-Operator. Dies ist ein unäroperator und erzeugt ein Ergebnis in dem alle 0 Bits in der Quelle Operand um 1 Bit konvertiert werden, und alle 1 Bit auf 0 Bits konvertiert werden.|
|`<<<`|Bitweiser Left Shift-Operator. Das Ergebnis ist, dass es sich bei der erste Operanden mit Bits nach links verschoben, durch die Anzahl der Bits im zweiten Operanden. Verschobene Position des höchstwertigen Bits werden nicht in die unwichtigsten Position gedreht. Die am niedrigstwertigen Bits werden mit Nullen aufgefüllt. Der Typ des zweiten Arguments ist `int32`.|
|`>>>`|Bitweise Rechtsschiebe-Operator. Das Ergebnis ist der erste Operand mit Bits nach rechts verschoben, um die Anzahl der Bits im zweiten Operanden. Bits die unwichtigsten Position verschoben werden nicht in die Position des höchstwertigen gedreht. Für Typen ohne Vorzeichen werden die höchstwertigen Bits mit Nullen aufgefüllt. Die höchstwertigen Bits werden für Typen mit Vorzeichen mit denen aufgefüllt. Der Typ des zweiten Arguments ist `int32`.|

Die folgenden Typen können mit bitweisen Operatoren verwendet werden: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, und `unativeint`.

## <a name="see-also"></a>Siehe auch
[Symbol- und Operatorenreferenz](index.md)

[Arithmetische Operatoren](arithmetic-operators.md)

[Boolesche Operatoren](boolean-operators.md)

