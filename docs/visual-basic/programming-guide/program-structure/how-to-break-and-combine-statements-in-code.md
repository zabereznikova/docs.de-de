---
title: 'Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf6b3ce7e5f9549ca04c4980bd3c91513b343ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)
Beim Schreiben von Code können Sie manchmal lange Anweisungen erstellen, die einer horizontalen Bildlauf im Code-Editor. Obwohl dies Einfluss auf die nicht der Code ausgeführt wird, es erschwert es für Sie oder andere Personen, den Code zu lesen, wie er auf dem Bildschirm angezeigt wird. In solchen Fällen sollten Sie erwägen, die lange Anweisung in mehrere Zeilen aufgeteilt.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Zu eine einzelne Anweisung mehrere Zeilen unterbrechen  
  
-   Verwenden Sie das Zeilenfortsetzungszeichen, also von einem Unterstrich (`_`), an dem Punkt, an dem Sie die Zeile umbrochen werden soll. Dem Unterstrich muss ein Leerzeichen direkt vorangestellt und ein Zeilenabschlusszeichen (Wagenrücklauf) direkt nachgestellt sein.  
  
    > [!NOTE]
    >  In einigen Fällen Wenn Sie das Zeilenfortsetzungszeichen weglassen wird Visual Basic-Compiler implizit die Anweisung in der nächsten Zeile des Codes fortgesetzt. Eine Liste der Syntaxelemente, die für die Sie das Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     Im folgenden Beispiel wird die Anweisung in vier Zeilen mit Zeilenfortsetzungszeichen beendet alle jedoch die letzte Zeile aufgeteilt.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Diese Sequenz können Code einfacher zu lesen, sowohl online als auch gedruckt.  
  
     Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein. Sie dürfen nicht es mit etwas anderes in derselben Zeile folgen.  
  
     Einige Einschränkungen vorhanden, wo Sie das Zeilenfortsetzungszeichen verwenden können. Beispielsweise kann nicht in der Mitte ein Argumentname Verwendung. Sie können eine Argumentliste, mit dem Zeilenfortsetzungszeichen unterbrechen, während die individuellen Namen eines der Argumente müssen jedoch intakt bleiben.  
  
     Einen Kommentar kann nicht fortgesetzt werden, mithilfe einer Zeilenfortsetzungszeichen. Der Compiler untersuchen nicht die Zeichen in einen Kommentar für eine besondere Bedeutung. Für einen mehrzeiligen Kommentar, wiederholen Sie das Kommentarsymbol (`'`) in jeder Zeile.  
  
 Zwar wird empfohlen, platzieren jede Anweisung in einer separaten Zeile [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Außerdem können Sie mit mehreren Anweisungen in der gleichen Zeile platzieren.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Mehrere Anweisungen in der gleichen Zeile platzieren  
  
-   Trennen Sie die Anweisungen durch einen Doppelpunkt (`:`), wie im folgenden Beispiel.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
