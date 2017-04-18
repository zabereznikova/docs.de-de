---
title: "Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic | Microsoft-Dokumentation"
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
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
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
ms.openlocfilehash: 9865e2d7d3786d289add3fa63b3db777317facdf
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic
Dieses Beispiel zeigt, wie Delegaten verwenden, um eine Prozedur an eine andere Prozedur übergeben wird.  
  
 Ein Delegat ist ein Typ, mit denen Sie wie jeden anderen Typ in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf eine Prozedurnamens zurück.  
  
 In diesem Beispiel wird eine Prozedur mit einem Delegatparameter, die einen Verweis auf eine andere Prozedur, die mit bezogen können die `AddressOf` Operator.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und entsprechender Prozeduren  
  
1.  Erstellen Sie einen Delegaten mit dem Namen `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewert, der übereinstimmen `MathOperator`, damit die Signaturen übereinstimmen.  
  
     [!code-vb[VbVbalrDelegates&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , die einen Delegaten als Parameter akzeptiert.  
  
     Diese Prozedur akzeptiert einen Verweis auf `AddNumbers` oder `SubtractNumbers`, da ihre Signaturen entsprechen den `MathOperator` Signatur.  
  
     [!code-vb[VbVbalrDelegates&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Erstellen Sie eine Prozedur mit dem Namen `Test` aufruft, `DelegateTest` einmal mit dem Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.  
  
     [!code-vb[VbVbalrDelegates&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Wenn `Test` wird aufgerufen, es zunächst zeigt das Ergebnis der `AddNumbers` handelnden auf `5` und `3`, also 8. Klicken Sie dann auf das Ergebnis des `SubtractNumbers` auf `9` und `3` angezeigt wird, also 6.  
  
## <a name="see-also"></a>Siehe auch  
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Gewusst wie: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
