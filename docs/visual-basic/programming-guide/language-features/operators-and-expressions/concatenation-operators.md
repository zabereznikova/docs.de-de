---
title: Verkettungsoperatoren in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: 124f0ca0cd01d7fd218fd89dfb78e70fe8aad9e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864933"
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
 Die [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) ist den primären Zweck von zwei Zahlen zu addieren. Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden. Der `+`-Operator verfügt über einen komplexen Satz an Regeln, die bestimmen, ob eine Addition oder Verkettung stattfindet, ob ein Compilerfehler signalisiert wird oder ob eine <xref:System.InvalidCastException>-Ausnahme bei Laufzeit ausgelöst wird.  
  
 Die [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) ist nur für definiert `String` -Operanden verwendet und erweitert seine Operanden, immer `String`, unabhängig von der Einstellung der `Option Strict`. Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.  
  
## <a name="performance-string-and-stringbuilder"></a>Leistung: Zeichenfolge und StringBuilder  
 Wenn Sie zahlreiche Manipulationen an einer Zeichenfolge durchführen, z. B. Verkettungen, Löschungen und Ersetzungen, kann Ihre Leistung von der <xref:System.Text.StringBuilder>-Klasse im <xref:System.Text>-Namespace profitieren. Sie benötigen eine zusätzliche Anweisung, um ein <xref:System.Text.StringBuilder>-Objekt zu erstellen und zu initialisieren, sowie eine weitere Anweisung, um den endgültigen Wert in einen `String` zu konvertieren. Diese Zeit können Sie jedoch wieder einholen, da <xref:System.Text.StringBuilder> eine schnellere Leistung bietet.  
  
## <a name="see-also"></a>Siehe auch

- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
