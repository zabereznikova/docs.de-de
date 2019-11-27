---
title: 'Gewusst wie: übergeben von Prozeduren an eine andere Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345246"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic
In diesem Beispiel wird gezeigt, wie Delegaten verwendet werden, um eine Prozedur an eine andere Prozedur zu übergeben.  
  
 Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können. Der `AddressOf`-Operator gibt ein Delegatobjekt zurück, wenn es auf einen Prozedur Namen angewendet wird.  
  
 Dieses Beispiel enthält eine Prozedur mit einem Delegatparameter, der einen Verweis auf eine andere Prozedur annehmen kann, die mit dem `AddressOf`-Operator abgerufen wird.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und der entsprechenden Prozeduren  
  
1. Erstellen Sie einen Delegaten mit dem Namen `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabe Werten, die mit denen `MathOperator`identisch sind, damit die Signaturen einander entsprechen.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die mit `MathOperator`übereinstimmt.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Erstellen Sie eine Prozedur mit dem Namen `DelegateTest`, die einen Delegaten als Parameter annimmt.  
  
     Diese Prozedur kann einen Verweis auf `AddNumbers` oder `SubtractNumbers`akzeptieren, da ihre Signaturen der `MathOperator` Signatur entsprechen.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Erstellen Sie eine Prozedur mit dem Namen `Test`, die `DelegateTest` einmal mit dem Delegaten für `AddNumbers` als Parameter aufruft, und wieder mit dem Delegaten für `SubtractNumbers` als Parameter.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Wenn `Test` aufgerufen wird, zeigt es zuerst das Ergebnis `AddNumbers` an, das auf `5` und `3`(8) wirkt. Anschließend wird das Ergebnis der `SubtractNumbers`, die auf `9` und `3` reagieren, angezeigt, d. h. 6.  
  
## <a name="see-also"></a>Siehe auch

- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Gewusst wie: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
