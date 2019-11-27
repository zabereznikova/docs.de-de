---
title: 'Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen'
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
ms.openlocfilehash: 36092eb597b5b20e1da42cd9d15ab8633636cfb1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344862"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)
Wenn eine Prozedur einen Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)deklariert, gibt Visual Basic dem Prozedur Code einen direkten Verweis auf das Programmier Element, das dem Argument im aufrufenden Code zugrunde liegt. Dies ermöglicht es der Prozedur, den Wert zu ändern, der dem Argument im aufrufenden Code zugrunde liegt. In einigen Fällen möchte der aufrufende Code möglicherweise vor einer solchen Änderung geschützt werden.  
  
 Sie können immer ein Argument vor der Änderung schützen, indem Sie den entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in der Prozedur deklarieren. Wenn Sie in der Lage sein möchten, ein bestimmtes Argument in einigen Fällen, aber nicht in anderen Fällen zu ändern, können Sie es `ByRef` deklarieren und den aufrufenden Code den Übergabe Mechanismus in jedem Aufruf bestimmen lassen. Dies geschieht, indem das entsprechende Argument in Klammern eingeschlossen wird, um es als Wert zu übergeben, oder dass es nicht in Klammern eingeschlossen wird, um es als Verweis zu übergeben. Weitere Informationen finden Sie unter Gewusst [wie: erzwingen, dass ein Argument als Wert weitergegeben wird](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Prozeduren, die eine Array Variable akzeptieren und deren Elemente verarbeiten. Die `increase` Prozedur fügt einem Element einfach ein Element hinzu. Die `replace` Prozedur weist dem Parameter `a()` ein neues Array zu und fügt dann jedem Element eine hinzu. Die Neuzuweisung wirkt sich jedoch nicht auf die zugrunde liegende Array Variable im aufrufenden Code aus.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 Der erste `MsgBox`-aufrufsbefehl zeigt "After Increase (n): 11, 21, 31, 41" an. Da das Array `n` ein Referenztyp ist, kann `increase` seine Member ändern, auch wenn der Übergabe Mechanismus `ByVal`ist.  
  
 Der zweite `MsgBox`-Aufrufe zeigt "After replace (n): 11, 21, 31, 41" an. Da `n` `ByVal`übermittelt wird, können `replace` die Variable `n` im aufrufenden Code nicht ändern, indem Sie Ihr ein neues Array zuweisen. Wenn `replace` die neue Array Instanz erstellt `k` und Sie der lokalen Variablen `a`zuweist, verliert Sie den Verweis auf `n`, die vom aufrufenden Code übermittelt werden. Wenn die Member von `a`geändert werden, ist nur das lokale Array `k` betroffen. Daher erhöht `replace` nicht die Werte der Array `n` im aufrufenden Code.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben. Es ist jedoch eine gute Programmier Übung, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) -oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jedem deklarierten Parameter einzuschließen. Dadurch wird Ihr Code leichter lesbar.  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
