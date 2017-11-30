---
title: Verkettungsoperatoren in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3a444cca76fbc41807b0c8b69bcbaedbd75c36eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="concatenation-operators-in-visual-basic"></a>Verkettungsoperatoren in Visual Basic
Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge. Es gibt zwei Verkettungsoperatoren: `+` und `&`. Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Diese Operatoren können auch `String`-Variablen verketten, wie das folgende Beispiel zeigt.  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Unterschiede zwischen den beiden Verkettungsoperatoren  
 Die [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) hat den primären Zweck Addition zweier Zahlen. Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden. Der `+`-Operator verfügt über einen komplexen Satz an Regeln, die bestimmen, ob eine Addition oder Verkettung stattfindet, ob ein Compilerfehler signalisiert wird oder ob eine <xref:System.InvalidCastException>-Ausnahme bei Laufzeit ausgelöst wird.  
  
 Die [&-Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) ist nur für definiert `String` Operanden, und es immer erweitert seine Operanden `String`, unabhängig von der Einstellung der `Option Strict`. Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.  
  
## <a name="performance-string-and-stringbuilder"></a>Leistung: Zeichenfolgen und StringBuilder  
 Wenn Sie zahlreiche Manipulationen an einer Zeichenfolge durchführen, z. B. Verkettungen, Löschungen und Ersetzungen, kann Ihre Leistung von der <xref:System.Text.StringBuilder>-Klasse im <xref:System.Text>-Namespace profitieren. Sie benötigen eine zusätzliche Anweisung, um ein <xref:System.Text.StringBuilder>-Objekt zu erstellen und zu initialisieren, sowie eine weitere Anweisung, um den endgültigen Wert in einen `String` zu konvertieren. Diese Zeit können Sie jedoch wieder einholen, da <xref:System.Text.StringBuilder> eine schnellere Leistung bietet.  
  
## <a name="see-also"></a>Siehe auch  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)  
 [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
