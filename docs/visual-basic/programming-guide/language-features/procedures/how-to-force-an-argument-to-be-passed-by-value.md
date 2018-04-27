---
title: 'Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30f5e5fe7b9c92f90673dc99a0e299136a38305b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)
In der Prozedurdeklaration des Übergabemechanismus. Wenn ein deklarierter Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic erwartet, dass das entsprechende Argument als Verweis zu übergeben. Dadurch wird das Verfahren zum Ändern des Werts, der das Programmierelement, die dem Argument im aufrufenden Code zugrunde liegt. Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie überschreiben die `ByRef` Übergabemechanismus in der Prozedur aufrufen, indem der Name des Arguments in Klammern einschließen. Die Klammern sind zusätzlich zu der Klammern, die die Argumentliste im Aufruf einschließen.  
  
 Der aufrufende Code kann nicht überschrieben werden eine [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Mechanismus.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>So erzwingen ein Argument als Wert übergeben werden  
  
-   Wenn der entsprechende Parameter deklariert wird `ByVal` in der Prozedur Sie brauchen keine zusätzlichen Schritte ausführen. Visual Basic erwartet bereits das Argument als Wert übergeben.  
  
-   Wenn der entsprechende Parameter deklariert wird `ByRef` setzen Sie in der Prozedur das Argument in Klammern in dem Prozeduraufruf.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `ByRef` Parameterdeklaration. Im Aufruf erzwingt `ByVal`, beachten Sie die beiden Ebenen von Klammern.  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist der `setNewString` Prozedur dessen Wert in der aufrufende Code kann nicht geändert werden und `MsgBox` "Kann nicht ersetzt werden, wenn ByVal überschritten" angezeigt. Wenn `str` nicht gesetzt in zusätzlichen Klammern, die Prozedur kann ggf. geändert und `MsgBox` zeigt "This is einen neuen Wert für das Argument InString."  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Wenn Sie keine Variable nach Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.  
  
 Der Standardwert in Visual Basic ist Argumenten als Wert übergeben. Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jeder deklarierte Parameter. Dadurch wird Ihr Code einfacher zu lesen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn eine Prozedur einen Parameter deklariert [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), die korrekte Ausführung des Codes abhängen, wird das zugrunde liegende Element im aufrufenden Code ändern können. Wenn der aufrufende Code diese Aufrufmechanismus überschreibt, indem das Argument in Klammern einschließen oder übergibt ein Argument nicht veränderbaren, kann nicht das Verfahren der zugrunde liegenden Elemente ändern. Dies kann unerwartete Ergebnisse im aufrufenden Code erzeugen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 In einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt, ist immer ein Sicherheitsrisiko dar. Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und es auf Gültigkeit zu überprüfen, vor der Verwendung vorbereitet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
