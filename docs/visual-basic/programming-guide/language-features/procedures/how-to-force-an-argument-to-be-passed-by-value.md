---
title: "Gewusst wie: erzwingen, dass ein Argument als Wert (Visual Basic) übergeben werden | Microsoft-Dokumentation"
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
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
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
ms.openlocfilehash: eea3466534f1797170ae4bc72afbcba899929911
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)
Den Übergabemechanismus der Prozedurdeklaration. Wenn ein Parameter deklariert ist [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erwartet, dass das entsprechende Argument als Verweis übergeben. Dadurch wird die Vorgehensweise zum Ändern des Werts des Programmierelements dem Argument im Aufrufcode zugrunde liegt. Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie überschreiben die `ByRef` übergeben Mechanismus in der Prozedur aufrufen, indem Sie den Namen des Arguments in Klammern einschließen. Die Klammern sind zusätzlich zu den Klammern, die die Argumentliste im Aufruf einschließen.  
  
 Der aufrufende Code kann nicht überschrieben werden eine [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Mechanismus.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Erzwingen Sie ein Argument als Wert übergeben werden  
  
-   Wenn der entsprechende Parameter deklariert ist `ByVal` in der Prozedur Sie brauchen keine zusätzlichen Schritte ausführen. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bereits erwartet, dass das Argument als Wert übergeben.  
  
-   Wenn der entsprechende Parameter deklariert ist `ByRef` im Verfahren setzen Sie das Argument im Prozeduraufruf in Klammern.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `ByRef` Parameterdeklaration. In den Aufruf, der erzwingt `ByVal`, beachten Sie die zwei Ebenen von Klammern.  
  
 [!code-vb[VbVbcnProcedures Nr.&39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist die `setNewString` Prozedur Wert in den aufrufenden Code, nicht ändern und `MsgBox` "Kann nicht ersetzt werden, wenn ByVal übergeben" angezeigt. Wenn `str` nicht gesetzt in zusätzlichen Klammern kann die Prozedur ändern, und `MsgBox` wird "Dies ist der Wert".  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Wenn Sie eine Variable als Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.  
  
 Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird. Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort in jeden deklarierten Parameter. Dadurch wird Ihr Code leichter zu lesen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn eine Prozedur einen Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), die richtige Ausführung des Codes abhängen, wird das zugrunde liegende Element im Aufrufcode ändern können. Wenn der Aufrufcode diesen Aufrufmechanismus überschreibt, indem das Argument in Klammern einschließen, oder es ein unveränderliches Argument übergibt, kann nicht in die Prozedur das zugrunde liegende Element ändern. Dies kann im Aufrufcode unerwartete Ergebnisse erzeugen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es ist immer ein potenzielles Risiko einer Prozedur so ändern Sie den Wert, der einem Argument im Aufrufcode zugrunde liegt. Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und bereiten Sie sich vor der Verwendung auf Gültigkeit überprüfen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)   
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)   
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
