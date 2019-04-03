---
title: 'Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c2305cd18cfaaa67355dfb342f22e39d37ae0e79
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818474"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic
Dieses Beispiel zeigt, wie Sie Delegaten verwenden, um eine Prozedur an eine andere Prozedur zu übergeben.  
  
 Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können. Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf den Namen einer Prozedur zurück.  
  
 Dieses Beispiel besteht aus eine Prozedur mit einem Delegate-Parameter, die einen Verweis auf eine andere Prozedur, die mit bezogen ergreifen können die `AddressOf` Operator.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und die entsprechenden Verfahren  
  
1.  Erstellen Sie einen Delegaten, mit dem Namen `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2.  Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewert, der übereinstimmen `MathOperator`, damit die Signaturen übereinstimmen.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3.  Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4.  Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , der einen Delegaten als Parameter akzeptiert.  
  
     Diese Prozedur akzeptiert einen Verweis auf `AddNumbers` oder `SubtractNumbers`, da die Signaturen übereinstimmen. die `MathOperator` Signatur.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5.  Erstellen Sie eine Prozedur mit dem Namen `Test` aufruft, `DelegateTest` einmal mit den Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Wenn `Test` wird aufgerufen, es zunächst zeigt das Ergebnis der `AddNumbers` -Eigenschaft `5` und `3`, dem ist 8. Klicken Sie dann das Ergebnis des `SubtractNumbers` , die auf `9` und `3` angezeigt wird, d.h. auf 6.  
  
## <a name="see-also"></a>Siehe auch

- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Vorgehensweise: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
