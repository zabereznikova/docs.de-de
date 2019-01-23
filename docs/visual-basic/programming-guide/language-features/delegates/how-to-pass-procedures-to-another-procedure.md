---
title: 'Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: cf5a8447cbedcd8071da98ac6763ff06eb608199
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506757"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic
Dieses Beispiel zeigt, wie Sie Delegaten verwenden, um eine Prozedur an eine andere Prozedur zu übergeben.  
  
 Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können. Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf den Namen einer Prozedur zurück.  
  
 Dieses Beispiel besteht aus eine Prozedur mit einem Delegate-Parameter, die einen Verweis auf eine andere Prozedur, die mit bezogen ergreifen können die `AddressOf` Operator.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und die entsprechenden Verfahren  
  
1.  Erstellen Sie einen Delegaten, mit dem Namen `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewert, der übereinstimmen `MathOperator`, damit die Signaturen übereinstimmen.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , der einen Delegaten als Parameter akzeptiert.  
  
     Diese Prozedur akzeptiert einen Verweis auf `AddNumbers` oder `SubtractNumbers`, da die Signaturen übereinstimmen. die `MathOperator` Signatur.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Erstellen Sie eine Prozedur mit dem Namen `Test` aufruft, `DelegateTest` einmal mit den Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Wenn `Test` wird aufgerufen, es zunächst zeigt das Ergebnis der `AddNumbers` -Eigenschaft `5` und `3`, dem ist 8. Klicken Sie dann das Ergebnis des `SubtractNumbers` , die auf `9` und `3` angezeigt wird, d.h. auf 6.  
  
## <a name="see-also"></a>Siehe auch
- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Vorgehensweise: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
