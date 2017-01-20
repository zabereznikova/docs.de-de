---
title: "Concatenation Operators in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "& operator [Visual Basic], concatenation"
  - "concatenation operators"
  - "operators [Visual Basic], concatenation"
  - "Visual Basic code, operators"
  - "+ operator [Visual Basic], concatenation"
  - "concatenation operators, Visual Basic strings"
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Concatenation Operators in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.  Es gibt zwei Verkettungsoperatoren: `+` und `&`.  Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.  
  
 [!CODE [Dim x As String = "Mic" & "ro" & "soft" Dim y As String = "Mic" + "ro" + "soft" ' The preceding statements set both x and y to "Microsoft".](Dim x As String = "Mic" & "ro" & "soft" Dim y As String = "Mic" + "ro" + "soft" ' The preceding statements set both x and y to "Microsoft".)]  
  
 Diese Operatoren können auch `String`\-Variablen verketten, wie das folgende Beispiel zeigt.  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## Unterschiede zwischen den beiden Verkettungsoperatoren  
 Der [\+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) dient dem primären Zweck, zwei Zahlen zu addieren.  Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden.  Der `+`\-Operator verfügt über einen komplexen Satz an Regeln, die bestimmen, ob eine Addition oder Verkettung stattfindet, ob ein Compilerfehler signalisiert wird oder ob eine <xref:System.InvalidCastException>\-Ausnahme bei Laufzeit ausgelöst wird.  
  
 Der [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) wird nur für `String`\-Operanden verwendet und erweitert seine Operanden immer auf `String`, unabhängig von der Einstellung für `Option Strict`.  Der `&`\-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.  
  
## Leistung: Zeichenfolge und StringBuilder  
 Wenn Sie zahlreiche Manipulationen an einer Zeichenfolge durchführen, z. B. Verkettungen, Löschungen und Ersetzungen, kann Ihre Leistung von der <xref:System.Text.StringBuilder>\-Klasse im <xref:System.Text>\-Namespace profitieren.  Sie benötigen eine zusätzliche Anweisung, um ein <xref:System.Text.StringBuilder>\-Objekt zu erstellen und zu initialisieren, sowie eine weitere Anweisung, um den endgültigen Wert in einen `String` zu konvertieren. Diese Zeit können Sie jedoch wieder einholen, da <xref:System.Text.StringBuilder> eine schnellere Leistung bietet.  
  
## Siehe auch  
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Types of String Manipulation Methods in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)