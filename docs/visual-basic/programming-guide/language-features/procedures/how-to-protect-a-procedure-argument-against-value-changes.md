---
title: "Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, arguments
- procedures, parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6e18f7ceefeec9c1f422d0eae4e727700ebd8b6e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)
Wenn eine Prozedur einen Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] übergibt der Prozedur einen direkten Verweis auf das Programmierelement, das dem Argument im Aufrufcode zugrunde liegt. Dies ermöglicht das Verfahren zum Ändern des Werts, der dem Argument im Aufrufcode zugrunde liegt. In einigen Fällen kann der aufrufende Code eine solche Änderung schützen möchten.  
  
 Sie können immer ein Argument vor einer Änderung schützen durch deklarieren den entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in der Prozedur. Wenn Sie ein Argument nur in bestimmten Fällen ändern können möchten, deklarieren Sie es `ByRef` , und lassen Sie den aufrufenden Code übergeben-Mechanismus in jedem Aufruf zu bestimmen. Hierzu wird das entsprechende Argument in Klammern für die Übergabe nach Wert einschließen oder es nicht in Klammern zur Übergabe nach Verweis einzuschließen. Weitere Informationen finden Sie unter [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente. Die `increase` Prozedur fügt einfach zu jedem Element. Die `replace` -Prozedur weist den Parameter ein neues Array `a()` und fügt dann jedem Element&1; hinzu. Die erneute Zuweisung wirkt sich jedoch nicht auf der zugrunde liegenden Arrayvariablen im Aufrufcode aus.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41". Da das Array `n` ist ein Verweistyp, `replace` kann seine Member ändern, obwohl die Übergabemechanismus ist `ByVal`.  
  
 Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 11, 21, 31, 41". Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` in den aufrufenden Code, indem Sie ein neues Array zuweisen. Wenn `replace` neue Arrayinstanz erstellt `k` und weist sie auf die lokale Variable `a`, verliert den Verweis auf `n` vom aufrufenden Code übergeben. Wenn sie die Mitglieder ändert `a`, nur auf das lokale Array `k` betroffen ist. Aus diesem Grund `replace` erhöht sich die Werte des Arrays nicht `n` im aufrufenden Code.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird. Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort in jeden deklarierten Parameter. Dadurch wird Ihr Code leichter zu lesen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)   
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)   
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
