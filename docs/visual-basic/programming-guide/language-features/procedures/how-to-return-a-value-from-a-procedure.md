---
title: 'Vorgehensweise: Abrufen eines Werts aus einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: cbc785a07aa8a7b299508a093e08d5d0510b838a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071377"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)

Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück, indem entweder eine-Anweisung ausgeführt wird `Return` oder eine- `Exit Function` oder-Anweisung auftritt `End Function` .  
  
### <a name="to-return-a-value-using-the-return-statement"></a>So geben Sie einen Wert mit der Return-Anweisung zurück  
  
1. Legen Sie eine `Return` -Anweisung an der Stelle ab, an der die Aufgabe der Prozedur abgeschlossen ist.  
  
2. Befolgen Sie das- `Return` Schlüsselwort mit einem Ausdruck, der den Wert ergibt, den Sie an den aufrufenden Code zurückgeben möchten.  
  
3. Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.  
  
     Mit der folgenden `Function` Prozedur wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet und an den aufrufenden Code zurückgegeben.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     Das folgende Beispiel zeigt einen typischen- `hypotenuse` Aufrufwert, der den zurückgegebenen Wert speichert.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>So geben Sie einen Wert mit der Funktion Exit oder End  
  
1. Weisen Sie in der Prozedur mindestens einen `Function` -Wert dem Namen der Prozedur zu.  
  
2. Wenn Sie eine- `Exit Function` oder `End Function` -Anweisung ausführen, gibt Visual Basic den Wert zurück, der zuletzt dem Namen der Prozedur zugewiesen wurde.  
  
3. Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.  
  
4. Sie können nur eine- `End Function` Anweisung in einer- `Function` Prozedur haben.  
  
     Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in der [Function-Anweisung](../../../language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweisen](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Function-Anweisung](../../../language-reference/statements/function-statement.md)
- [Return-Anweisung](../../../language-reference/statements/return-statement.md)
- [Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)
- [Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
