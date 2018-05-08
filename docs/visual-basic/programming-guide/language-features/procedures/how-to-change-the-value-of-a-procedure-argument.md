---
title: 'Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 118dd3389804794801d39e7d67b68ab195bbad3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)
Wenn Sie eine Prozedur aufrufen, entspricht jedes Argument, das Sie angeben eines Parameters in der Prozedur definiert. In einigen Fällen kann der Code die Prozedur den Wert, der ein Argument im aufrufenden Code zugrunde liegt, ändern. In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.  
  
 Wenn Sie die Prozedur aufrufen, Visual Basic ermöglicht eine lokale Kopie jeder übergebene Argument [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Für jedes Argument übergebenen [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic Code der Prozedur bietet einen direkten Verweis auf das Programmierelement, die dem Argument im aufrufenden Code zugrunde liegt.  
  
 Wenn das zugrunde liegende Element im aufrufenden Code ein Element geändert werden kann wird und das Argument übergeben `ByRef`, Code der Prozedur mithilfe der direkten Verweis um der Wert des Elements im aufrufenden Code zu ändern.  
  
## <a name="changing-the-underlying-value"></a>Ändern des zugrunde liegenden Werts  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Zum Ändern des zugrunde liegenden Werts eines Prozedurarguments im aufrufenden code  
  
1.  Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter an das Argument entspricht.  
  
2.  Übergeben Sie in der aufrufende Code ein änderbares Programmierelement als Argument.  
  
3.  Schließen Sie in den aufrufenden Code nicht das Argument in Klammern in der Argumentliste.  
  
4.  Verwenden Sie im Code Prozedur den Namen des Parameters an das zugrunde liegende Element im aufrufenden Code einen Wert zuweisen.  
  
 Siehe das Beispiel weiter unten veranschaulicht.  
  
## <a name="changing-local-copies"></a>Ändern von lokalen Kopien  
 Wenn das zugrunde liegende Element in der aufrufende Code eine nicht veränderbaren ist oder wenn das Argument übergeben, wird `ByVal`, dessen Wert in den aufrufenden Code von die Prozedur kann nicht geändert werden können. Die Prozedur kann jedoch die lokale Kopie der ein derartiges Argument ändern.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>So ändern Sie die Kopie eines Prozedurarguments im Code Prozedur  
  
1.  Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter an das Argument entspricht.  
  
     - oder -   
  
     Setzen Sie in den aufrufenden Code das Argument in Klammern in der Argumentliste. Dies zwingt Visual Basic, um das Argument als Wert übergeben, auch wenn der entsprechende Parameter gibt `ByRef`.  
  
2.  Verwenden Sie im Code Prozedur der Name des Parameters, um die lokale Kopie des Arguments einen Wert zuzuweisen. Der zugrunde liegenden Wert im aufrufenden Code wird nicht geändert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente. Die `increase` Verfahren einfach zu jedem Element hinzufügt. Die `replace` -Prozedur weist den Parameter ein neues Array `a()` , und klicken Sie dann auf jedes Element hinzugefügt.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41". Da das Array `n` ist ein Verweistyp `replace` seiner Elemente, können geändert werden, obwohl der Übergabemechanismus ist `ByVal`.  
  
 Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 101, 201, 301". Da `n` übergeben `ByRef`, `replace` ändern Sie die Variable `n` in den aufrufenden Code, und weisen Sie ein neues Array zu. Da `n` ist ein Verweistyp `replace` Membern können auch ändern.  
  
 Sie können verhindern, dass die Prozedur die Variable im aufrufenden Code ändern. Finden Sie unter [wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Wenn Sie keine Variable nach Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.  
  
 Der Standardwert in Visual Basic ist Argumenten als Wert übergeben. Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jeder deklarierte Parameter. Dadurch wird Ihr Code einfacher zu lesen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 In einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt, ist immer ein Sicherheitsrisiko dar. Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und es auf Gültigkeit zu überprüfen, vor der Verwendung vorbereitet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
