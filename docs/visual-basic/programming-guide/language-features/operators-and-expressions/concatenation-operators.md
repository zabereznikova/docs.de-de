---
title: Verkettungsoperatoren in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators, Visual Basic strings
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fa11f1dcff2c333861596cbac03391403cf962c1
ms.lasthandoff: 03/13/2017

---
# <a name="concatenation-operators-in-visual-basic"></a>Verkettungsoperatoren in Visual Basic
Verkettungsoperatoren verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge. Es gibt zwei Verkettungsoperatoren: `+` und `&`. Beide führen einen grundlegende Verkettungsvorgang durch, wie das nachfolgende Beispiel zeigt.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Diese Operatoren können auch `String`-Variablen verketten, wie das folgende Beispiel zeigt.  
  
 [!code-vb[VbVbalrOperators&#76;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Unterschiede zwischen den beiden Verkettungsoperatoren  
 Die [+-Operator](../../../../visual-basic/language-reference/operators/addition-operator.md) ist den primären Zweck von zwei Zahlen hinzugefügt wurden. Damit können jedoch auch numerische Operanden mit Zeichenfolgenoperanden verkettet werden. Die `+` Operator verfügt über einen komplexen Satz von Regeln, die bestimmen, ob die hinzufügen, verkettet, ein Compilerfehler signalisiert oder eine Laufzeit <xref:System.InvalidCastException>Ausnahme.</xref:System.InvalidCastException>  
  
 Die [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) ist nur für definiert `String` -Operanden verwendet und erweitert seine Operanden zu immer `String`, unabhängig von der Einstellung der `Option Strict`. Der `&`-Operator wird für die Zeichenfolgenverkettung empfohlen, da er ausschließlich für Zeichenfolgen definiert wurde und da er die Gefahr einer unbeabsichtigten Konvertierung reduziert.  
  
## <a name="performance-string-and-stringbuilder"></a>Leistung: Zeichenfolgen und StringBuilder  
 Wenn Sie eine große Anzahl von Manipulationen an einer Zeichenfolge, z. B. Verkettungen, löschungen und Ersetzungen, führen Sie die Leistung möglicherweise Gewinn der <xref:System.Text.StringBuilder>-Klasse in die <xref:System.Text>Namespace.</xref:System.Text> </xref:System.Text.StringBuilder> Dauert es eine zusätzliche Anweisung erstellt und initialisiert ein <xref:System.Text.StringBuilder>Objekt und eine andere Anweisung für den endgültigen Wert zu konvertieren einer `String`, aber diesmal kann wiederhergestellt werden, da <xref:System.Text.StringBuilder>schneller ausführen können.</xref:System.Text.StringBuilder> </xref:System.Text.StringBuilder>  
  
## <a name="see-also"></a>Siehe auch  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Typen von Zeichenfolgenbearbeitungsmethoden in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
