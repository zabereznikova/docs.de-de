---
title: "Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e8e205f5238aab39aa92574bc5c680e68cc8a81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic
Dieses Beispiel zeigt, wie Delegaten verwenden, um eine Prozedur an eine andere Prozedur übergeben wird.  
  
 Ein Delegat ist ein Typ, wie jeder andere Typ, in denen können [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf eine Prozedurnamens zurück.  
  
 In diesem Beispiel besteht aus einer Prozedur mit einem Delegatparameter, der einen Verweis auf eine andere Prozedur, durch erzielt werden kann die `AddressOf` Operator.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und dem entsprechenden Verfahren  
  
1.  Erstellen Sie einen Delegaten mit dem Namen `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewerten, die denen des entsprechen `MathOperator`, damit die Signaturen übereinstimmen.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , das einen Delegaten als Parameter akzeptiert.  
  
     Diese Prozedur kann einen Verweis auf akzeptieren `AddNumbers` oder `SubtractNumbers`, da ihre Signaturen entsprechen den `MathOperator` Signatur.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Erstellen Sie eine Prozedur mit dem Namen `Test` damaligen `DelegateTest` einmal mit der Delegat für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Wenn `Test` wird aufgerufen, es zuerst zeigt das Ergebnis der `AddNumbers` handelnden auf `5` und `3`, also in 8. Klicken Sie dann das Ergebnis des `SubtractNumbers` , agiert `9` und `3` angezeigt wird, ist 6.  
  
## <a name="see-also"></a>Siehe auch  
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Gewusst wie: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
