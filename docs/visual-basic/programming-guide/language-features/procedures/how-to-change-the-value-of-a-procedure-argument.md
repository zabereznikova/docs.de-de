---
title: 'Vorgehensweise: Ändern des Werts eines Prozedurarguments (Visual Basic)'
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
ms.openlocfilehash: a56bdf888163c9559b87e857abb33522c547ed45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665831"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Vorgehensweise: Ändern des Werts eines Prozedurarguments (Visual Basic)
Wenn Sie eine Prozedur aufrufen, entspricht jedes Argument, das Sie angeben, einer der Parameter in der Prozedur definiert. In einigen Fällen kann der Code der Prozedur den Wert, der zugrunde liegenden Argument im aufrufenden Code ändern. In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.  
  
 Wenn Sie die Prozedur aufrufen, handelt es sich bei Visual Basic ermöglicht eine lokale Kopie von jedem Argument, das übergeben wird [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Für jedes Argument übergebenen [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic bietet der Code der Prozedur einen direkten Verweis auf das Programmierelement zugrunde liegenden Arguments im aufrufenden Code.  
  
 Wenn das zugrunde liegende Element im aufrufenden Code ein Element geändert werden kann wird, und das Argument übergeben wird `ByRef`, der Code der Prozedur können den direkten Verweis so ändern Sie den Wert des Elements im aufrufenden Code.  
  
## <a name="changing-the-underlying-value"></a>Den zugrunde liegenden Wert ändern  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Zum Ändern des zugrunde liegenden Werts eines Prozedurarguments im aufrufenden code  
  
1. Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter mit dem Argument entspricht.  
  
2. Übergeben Sie im aufrufenden Code ein änderbares Programmierelement als Argument ein.  
  
3. Schließen Sie in den aufrufenden Code nicht das Argument in Klammern in der Argumentliste.  
  
4. Können Sie der Name des Parameters im Code Prozedur um das zugrunde liegende Element im aufrufenden Code einen Wert zuzuweisen.  
  
 Siehe das Beispiel weiter unten veranschaulicht.  
  
## <a name="changing-local-copies"></a>Ändern von lokalen Kopien  
 Wenn das zugrunde liegende Element im aufrufenden Code eine als nicht änderbar ist, oder wenn das Argument übergeben wird `ByVal`, die Prozedur Wert im aufrufenden Code nicht ändern kann. Die Prozedur kann jedoch die lokale Kopie der derartiges Argument ändern.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>So ändern Sie die Kopie eines Prozedurarguments im Code Prozedur  
  
1. Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter mit dem Argument entspricht.  
  
     - oder -   
  
     Setzen Sie in den aufrufenden Code das Argument in Klammern in der Argumentliste. Dies zwingt Visual Basic, um das Argument als Wert übergeben, selbst wenn der entsprechende Parameter gibt an, `ByRef`.  
  
2. Können Sie der Name des Parameters im Code Prozedur um die lokale Kopie des Arguments einen Wert zuzuweisen. Der zugrunde liegenden Wert im aufrufenden Code wird nicht geändert werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Verfahren, die eine Arrayvariable und ausgeführt werden, die Elemente. Die `increase` Verfahren einfach zu jedem Element hinzufügt. Die `replace` Prozedur weist ein neues Array, an den Parameter `a()` , und klicken Sie dann auf die einzelnen Elemente hinzugefügt.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Die erste `MsgBox` aufrufen, zeigt "nach increase(n):: 11, 21, 31, 41". Da das Array `n` ist ein Verweistyp, `replace` können ihre Member, ändern, auch wenn der Übergabemechanismus ist `ByVal`.  
  
 Die zweite `MsgBox` aufrufen, zeigt "nach Replace(n):: 101, 201, 301". Da `n` übergeben wird `ByRef`, `replace` ändern können Sie die Variable `n` im aufrufenden Code und weisen Sie ein neues Array zuzuweisen. Da `n` ist ein Verweistyp, `replace` können Member auch ändern.  
  
 Sie können verhindern, dass das Verfahren ändern die Variable im aufrufenden Code. Weitere Informationen finden Sie unter [How to: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Wenn Sie eine Variable als Verweis übergeben, müssen Sie verwenden die `ByRef` Schlüsselwort, um diesen Mechanismus angeben.  
  
 Der Standardwert in Visual Basic ist, Argumente als Wert übergeben. Allerdings ist es guter Programmierstil, auch die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für jeden deklarierten Parameter. Dadurch wird Ihr Code einfacher zu lesen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es ist immer ein potenzielles Risiko einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt. Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und auf Gültigkeit überprüft werden vor der Verwendung vorbereitet werden.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
