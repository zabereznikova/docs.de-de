---
title: 'Gewusst wie: umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
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
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 840036a91f430f72e0258b8be466770f2855a58f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)
Beim Schreiben von Code können Sie manchmal lange Anweisungen erstellen, die einer horizontalen Bildlauf im Code-Editor. Obwohl dies Einfluss auf die keine Ausführung von Code, erschwert für Sie oder andere Personen zum Lesen des Codes, wie er auf dem Bildschirm angezeigt wird. In solchen Fällen sollten Sie erwägen, die lange Anweisung in mehrere Zeilen unterteilt.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Eine einzelne Anweisung in mehrere Zeilen aufgeteilt  
  
-   Verwenden Sie das Zeilenfortsetzungszeichen, wird ein Unterstrich (`_`), an dem Punkt, an dem die Zeile umbrochen werden soll. Dem Unterstrich muss ein Leerzeichen direkt vorangestellt und ein Zeilenabschlusszeichen (Wagenrücklauf) direkt nachgestellt sein.  
  
    > [!NOTE]
    >  In einigen Fällen Wenn Sie das Zeilenfortsetzungszeichen weglassen wird Visual Basic-Compiler implizit die Anweisung in der nächsten Zeile des Codes fortgesetzt. Eine Liste der Elemente der Syntax für die Sie das Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     Im folgenden Beispiel wird die Anweisung in vier Zeilen mit Zeilenfortsetzungszeichen beendet alle jedoch die letzte Zeile aufgeteilt.  
  
     [!code-vb[VbVbcnConventions&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     Mit dieser Sequenz wird der Code einfacher zu lesen, sowohl online als auch gedruckt.  
  
     Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein. Sie können nicht es mit etwas anderes in derselben Zeile folgen.  
  
     Einige Einschränkungen vorhanden, wo Sie das Zeilenfortsetzungszeichen verwenden können. Beispielsweise kann nicht in der Mitte ein Argumentname Verwendung. Sie können eine Argumentliste mit dem Zeilenfortsetzungszeichen unterbrechen, aber die einzelnen Argumente müssen intakt bleiben.  
  
     Einen Kommentar kann nicht fortgesetzt werden, mit einem Zeilenfortsetzungszeichen. Der Compiler untersuchen nicht die Zeichen in einem Kommentar für besondere Bedeutung. Für einen mehrzeiligen Kommentar, wiederholen Sie das Kommentarsymbol (`'`) in jeder Zeile.  
  
 Zwar wird empfohlen, jede Anweisung in einer separaten Zeile platzieren [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] darüber hinaus können Sie mehrere Anweisungen in der gleichen Zeile platzieren.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Um mehrere Anweisungen in der gleichen Zeile platzieren  
  
-   Trennen Sie die Anweisungen mit einem Doppelpunkt (`:`), wie im folgenden Beispiel.  
  
     [!code-vb[VbVbcnConventions&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
