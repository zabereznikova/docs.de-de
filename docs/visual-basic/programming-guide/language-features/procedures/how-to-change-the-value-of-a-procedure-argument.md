---
title: "Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic) | Microsoft-Dokumentation"
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
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
ms.openlocfilehash: 6c42a50b75bcc70ae0a3f70771b9e1f85626004b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)
Wenn Sie eine Prozedur aufrufen, entspricht jedes Argument, das Sie Bereitstellen einer der in der Prozedur definierten Parameter. In einigen Fällen kann der Code der Prozedur den Wert, der einem Argument im Aufrufcode zugrunde liegt ändern. In anderen Fällen kann die Prozedur nur ihre lokale Kopie eines Arguments ändern.  
  
 Beim Aufrufen der Prozedur [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wird eine lokale Kopie jedes Argument übergeben [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). Für jedes Argument übergebenen [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] übergibt der Prozedur einen direkten Verweis auf das Programmierelement, das dem Argument im Aufrufcode zugrunde liegt.  
  
 Wenn das zugrunde liegende Element im Aufrufcode ein veränderbares Element ist und das Argument übergeben wird `ByRef`, Code der Prozedur können den direkten Verweis der Wert des Elements im Aufrufcode ändern.  
  
## <a name="changing-the-underlying-value"></a>Ändern des zugrunde liegenden Werts  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>So ändern Sie den zugrunde liegenden Wert eines Prozedurarguments im Aufrufcode  
  
1.  Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter entspricht dem Argument.  
  
2.  Übergeben Sie in den Aufrufcode ein änderbares Programmierelement als Argument.  
  
3.  Schließen Sie in den aufrufenden Code nicht das Argument in Klammern in der Argumentliste.  
  
4.  Verwenden Sie im Code Prozedur den Namen des Parameters an das zugrunde liegende Element im Aufrufcode einen Wert zuzuweisen.  
  
 Siehe das Beispiel weiter unten veranschaulicht.  
  
## <a name="changing-local-copies"></a>Ändern von lokalen Kopien  
 Wenn das zugrunde liegende Element im Aufrufcode ein nicht änderbares Element ist oder wenn das Argument übergeben wird `ByVal`, die Prozedur Wert im aufrufenden Code nicht ändern. Die Prozedur kann jedoch die lokale Kopie eines solchen Arguments ändern.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>So ändern Sie die Kopie eines Prozedurarguments im Prozedurcode  
  
1.  Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter entspricht dem Argument.  
  
     - oder -   
  
     Setzen Sie in den aufrufenden Code das Argument in Klammern in der Argumentliste. Dies zwingt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , das Argument als Wert zu übergeben, auch wenn der entsprechende Parameter gibt `ByRef`.  
  
2.  Verwenden Sie im Code Prozedur den Parameternamen, um die lokale Kopie des Arguments einen Wert zuzuweisen. Der zugrunde liegende Wert im Aufrufcode wird nicht geändert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente. Die `increase` Prozedur fügt einfach zu jedem Element. Die `replace` -Prozedur weist den Parameter ein neues Array `a()` und fügt dann jedem Element&1; hinzu.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures Nr.&36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41". Da das Array `n` ist ein Verweistyp, `replace` kann seine Member ändern, obwohl die Übergabemechanismus ist `ByVal`.  
  
 Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 101, 201, 301". Da `n` übergeben `ByRef`, `replace` ändern Sie die Variable `n` in den aufrufenden Code, und weisen Sie ein neues Array. Da `n` ist ein Verweistyp `replace` Membern können auch ändern.  
  
 Sie können verhindern, dass die Prozedur die Variable im aufrufenden Code ändern. Finden Sie unter [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Wenn Sie eine Variable als Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.  
  
 Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird. Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort in jeden deklarierten Parameter. Dadurch wird Ihr Code leichter zu lesen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es ist immer ein potenzielles Risiko einer Prozedur so ändern Sie den Wert, der einem Argument im Aufrufcode zugrunde liegt. Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und bereiten Sie sich vor der Verwendung auf Gültigkeit überprüfen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)   
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)   
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
