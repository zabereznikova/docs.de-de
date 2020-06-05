---
title: Verkettungsoperatoren
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: c123438a86a2c3293a99770107d970535fcdbdf8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388789"
---
# <a name="concatenation-operators-in-visual-basic"></a>Verkettungsoperatoren in Visual Basic

Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge. Es gibt zwei Verkettungsoperatoren: `+` und `&`. Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.

```vb
Dim x As String = "Mic" & "ro" & "soft"
Dim y As String = "Mic" + "ro" + "soft"
' The preceding statements set both x and y to "Microsoft".
```

Diese Operatoren können auch `String`-Variablen verketten, wie das folgende Beispiel zeigt.

[!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]

## <a name="differences-between-the-two-concatenation-operators"></a>Unterschiede zwischen den beiden Verkettungsoperatoren

Der [+-Operator](../../../language-reference/operators/addition-operator.md) hat den Hauptzweck, zwei Zahlen hinzuzufügen. Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden. Der `+`-Operator verfügt über einen komplexen Satz an Regeln, die bestimmen, ob eine Addition oder Verkettung stattfindet, ob ein Compilerfehler signalisiert wird oder ob eine <xref:System.InvalidCastException>-Ausnahme bei Laufzeit ausgelöst wird.

Der [&-Operator](../../../language-reference/operators/concatenation-operator.md) ist nur für `String` Operanden definiert und erweitert seine Operanden immer auf `String` , unabhängig von der Einstellung von `Option Strict` . Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.

## <a name="performance-string-and-stringbuilder"></a>Leistung: String und StringBuilder

Wenn Sie zahlreiche Manipulationen an einer Zeichenfolge durchführen, z. B. Verkettungen, Löschungen und Ersetzungen, kann Ihre Leistung von der <xref:System.Text.StringBuilder>-Klasse im <xref:System.Text>-Namespace profitieren. Sie benötigen eine zusätzliche Anweisung, um ein <xref:System.Text.StringBuilder>-Objekt zu erstellen und zu initialisieren, sowie eine weitere Anweisung, um den endgültigen Wert in einen `String` zu konvertieren. Diese Zeit können Sie jedoch wieder einholen, da <xref:System.Text.StringBuilder> eine schnellere Leistung bietet.

## <a name="see-also"></a>Weitere Informationen

- [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)
- [Verschiedene Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic](../strings/types-of-string-manipulation-methods.md)
- [Arithmetische Operatoren in Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](logical-and-bitwise-operators.md)
