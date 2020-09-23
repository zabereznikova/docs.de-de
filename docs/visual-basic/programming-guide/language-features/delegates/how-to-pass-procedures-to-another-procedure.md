---
title: 'Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 3a7a653bbf238b50e3c7339da76df0f68ab9b59f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085788"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic

In diesem Beispiel wird gezeigt, wie Delegaten verwendet werden, um eine Prozedur an eine andere Prozedur zu übergeben.  
  
 Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können. Der- `AddressOf` Operator gibt ein Delegatobjekt zurück, wenn es auf einen Prozedur Namen angewendet wird.  
  
 Dieses Beispiel enthält eine Prozedur mit einem Delegatparameter, der einen Verweis auf eine andere Prozedur annehmen kann, die mit dem-Operator abgerufen wird `AddressOf` .  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und der entsprechenden Prozeduren  
  
1. Erstellen Sie einen Delegaten namens `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Erstellen Sie eine Prozedur `AddNumbers` mit dem Namen mit Parametern und Rückgabe Werten, die mit denen von identisch `MathOperator` sind, damit die Signaturen einander entsprechen.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Erstellen Sie eine Prozedur `SubtractNumbers` mit dem Namen mit einer Signatur, die entspricht `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , die einen Delegaten als Parameter annimmt.  
  
     Diese Prozedur kann einen Verweis auf `AddNumbers` oder akzeptieren `SubtractNumbers` , da ihre Signaturen der `MathOperator` Signatur entsprechen.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Erstellen Sie eine Prozedur `Test` mit dem Namen, die `DelegateTest` einmal mit dem Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter aufruft.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Wenn `Test` aufgerufen wird, zeigt es zuerst das Ergebnis der Durchsetzung von `AddNumbers` für `5` und `3` , d. h. 8. Anschließend wird das Ergebnis der Durchsetzung von `SubtractNumbers` unter `9` und `3` angezeigt, d. h. 6.  
  
## <a name="see-also"></a>Siehe auch

- [Delegaten](index.md)
- [AddressOf-Operator](../../../language-reference/operators/addressof-operator.md)
- [Delegate-Anweisung](../../../language-reference/statements/delegate-statement.md)
- [Vorgehensweise: Aufrufen einer Delegatenmethode](how-to-invoke-a-delegate-method.md)
