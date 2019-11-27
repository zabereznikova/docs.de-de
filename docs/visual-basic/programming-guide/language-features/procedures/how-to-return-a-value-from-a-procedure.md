---
title: 'Gewusst wie: Abrufen eines Werts aus einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346027"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)
Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück, indem entweder eine `Return`-Anweisung ausgeführt wird oder eine `Exit Function`-oder `End Function`-Anweisung auftritt.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>So geben Sie einen Wert mit der Return-Anweisung zurück  
  
1. Fügen Sie eine `Return`-Anweisung an der Stelle ein, an der die Aufgabe der Prozedur abgeschlossen ist.  
  
2. Befolgen Sie das `Return`-Schlüsselwort mit einem Ausdruck, der den Wert ergibt, den Sie an den aufrufenden Code zurückgeben möchten.  
  
3. Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.  
  
     Die folgende `Function` Prozedur berechnet die längste Seite (Hypotenuse) eines Rechts Dreiecks und gibt Sie an den aufrufenden Code zurück.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Das folgende Beispiel zeigt einen typischen-`hypotenuse`, der den zurückgegebenen Wert speichert.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>So geben Sie einen Wert mit der Funktion Exit oder End  
  
1. Weisen Sie in der `Function` Prozedur mindestens einen-Wert dem Namen der Prozedur zu.  
  
2. Wenn Sie eine `Exit Function`-oder `End Function`-Anweisung ausführen, gibt Visual Basic den Wert zurück, der zuletzt dem Namen der Prozedur zugewiesen wurde.  
  
3. Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.  
  
4. Sie können in einer `Function` Prozedur nur eine `End Function`-Anweisung ausführen.  
  
     Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in der [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Return-Anweisung](../../../../visual-basic/language-reference/statements/return-statement.md)
- [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)
- [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
