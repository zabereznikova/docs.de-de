---
title: 'Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)'
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
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 70378b57c6d3af5a98e0ba9c6e3aebc319561b1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665740"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)
Wenn eine Prozedur einen Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic bietet der Code der Prozedur einen direkten Verweis auf das Programmierelement zugrunde liegenden Arguments im aufrufenden Code. Dies ermöglicht das Verfahren zum Ändern des Werts, der dem Argument im aufrufenden Code zugrunde liegt. In einigen Fällen kann der aufrufende Code eine solche Änderung schützen möchten.  
  
 Sie können immer ein Argument aus schützen, indem der entsprechende Parameter deklarieren [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in der Prozedur. Wenn Sie ein bestimmtes Argument in einigen Fällen aber in anderen ändern möchten, deklarieren Sie es `ByRef` und lassen Sie den aufrufenden Code, der den Übergabemechanismus bei jedem Aufruf zu bestimmen. Hierzu setzen Sie das entsprechende Argument in Klammern einschließen, um es als Wert übergeben, oder setzt ihn nicht in Klammern einschließen, um es als Verweis zu übergeben. Weitere Informationen finden Sie unter [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Verfahren, die eine Arrayvariable und ausgeführt werden, die Elemente. Die `increase` Verfahren einfach zu jedem Element hinzufügt. Die `replace` Prozedur weist ein neues Array, an den Parameter `a()` , und klicken Sie dann auf die einzelnen Elemente hinzugefügt. Die neuzuweisung wirkt sich jedoch nicht auf die zugrunde liegende Arrayvariable im aufrufenden Code aus.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Die erste `MsgBox` aufrufen, zeigt "nach increase(n):: 11, 21, 31, 41". Da das Array `n` ist ein Verweistyp, `increase` können ihre Member, ändern, auch wenn der Übergabemechanismus ist `ByVal`.  
  
 Die zweite `MsgBox` aufrufen, zeigt "nach Replace(n):: 11, 21, 31, 41". Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` im aufrufenden Code, indem Sie ein neues Array zuweisen. Wenn `replace` neuen Arrayinstanz erstellt `k` und weist sie auf die lokale Variable `a`, er verliert den Verweis auf `n` vom aufrufenden Code übergeben. Wenn sie die Mitglieder der ändert `a`, nur das lokale Array `k` betroffen ist. Aus diesem Grund `replace` erhöht sich die Werte des Arrays nicht `n` im aufrufenden Code.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Der Standardwert in Visual Basic ist, Argumente als Wert übergeben. Allerdings ist es guter Programmierstil, auch die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für jeden deklarierten Parameter. Dadurch wird Ihr Code einfacher zu lesen.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
