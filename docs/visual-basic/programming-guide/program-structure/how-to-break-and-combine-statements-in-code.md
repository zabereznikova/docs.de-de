---
title: 'Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb._
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
ms.openlocfilehash: d3656b924ebaca67c90dc602701c4cef9ce088b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648782"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)
Wenn Ihr Code schreiben, können Sie gelegentlich lange Anweisungen erstellen, die erfordern, horizontalen Bildlauf im Code-Editor. Obwohl dies Einfluss auf die nicht Ihr Code ausgeführt wird, erleichtert es schwierig für Sie oder andere Personen Lesen des Codes, wie er auf dem Bildschirm angezeigt wird. In solchen Fällen sollten Sie erwägen, die lange Anweisung in mehrere Zeilen unterteilt.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>Eine einzelne Anweisung in mehrere Zeilen aufteilen  
  
- Verwenden Sie das Zeilenfortsetzungszeichen, wird ein Unterstrich (`_`), an dem Punkt, an dem die Zeile umbrochen werden soll. Dem Unterstrich muss ein Leerzeichen direkt vorangestellt und ein Zeilenabschlusszeichen (Wagenrücklauf) direkt nachgestellt sein.  
  
    > [!NOTE]
    >  In einigen Fällen Wenn Sie das Zeilenfortsetzungszeichen weglassen wird Visual Basic-Compiler implizit die Anweisung in der nächsten Zeile des Codes fortgesetzt. Eine Liste der Syntaxelemente, die für die Sie dem Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     Im folgenden Beispiel wird die Anweisung in vier Zeilen mit Zeilenfortsetzungszeichen beendet alle jedoch die letzte Zeile aufgeteilt.  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     Verwenden diese Sequenz wird Ihr Code einfacher zu lesen, sowohl online als auch gedruckt.  
  
     Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein. Sie können nicht es mit anderen Elementen in der gleichen Zeile folgen.  
  
     Einige Einschränkungen vorhanden, wo Sie das Zeilenfortsetzungszeichen verwenden können. Beispielsweise kann nicht in der Mitte ein Argumentname Verwendung. Sie können eine Argumentliste, mit dem Zeilenfortsetzungszeichen unterbrechen, aber die einzelnen Argumente müssen intakt bleiben.  
  
     Einen Kommentar kann nicht fortgesetzt werden, mithilfe einer Zeilenfortsetzungszeichen. Der Compiler überprüfen nicht Sie die Zeichen in einen Kommentar für eine besondere Bedeutung. Für einen mehrzeiligen Kommentar, wiederholen Sie das Kommentarsymbol (`'`) in jeder Zeile.  
  
 Obwohl jede Anweisung in einer eigenen Zeile platzieren die empfohlene Methode ist, ermöglicht Visual Basic auch Sie mehrere Anweisungen in der gleichen Zeile platzieren.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>Mehrere Anweisungen in der gleichen Zeile platzieren  
  
- Trennen Sie die Anweisungen durch einen Doppelpunkt (`:`), wie im folgenden Beispiel.  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Siehe auch

- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
