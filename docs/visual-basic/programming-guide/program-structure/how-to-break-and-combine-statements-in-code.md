---
title: 'Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code'
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
ms.openlocfilehash: c78cbeaa5c2df2d4f2e3cce2b5b3fb8048ff3388
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403251"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)

Wenn Sie Ihren Code schreiben, können Sie häufig lange Anweisungen erstellen, die den horizontalen Bildlauf im Code-Editor erfordern. Dies wirkt sich nicht auf die Art und Weise aus, in der der Code ausgeführt wird. es ist jedoch schwierig, den Code so zu lesen, wie er auf dem Monitor angezeigt wird. In solchen Fällen sollten Sie die Unterbrechung der einzelnen langen Anweisung in mehrere Zeilen in Erwägung gezogen.

## <a name="to-break-a-single-statement-into-multiple-lines"></a>So brechen Sie eine einzelne Anweisung in mehrere Zeilen um

Verwenden Sie das Zeilen Fortsetzungs Zeichen, bei dem es sich `_` um einen Unterstrich () handelt, an der Stelle, an der Sie die Zeile unterbrechen möchten. Dem Unterstrich muss ein Leerzeichen unmittelbar vorangestellt sein, und es muss unmittelbar ein Zeichen für den Zeilen Abschluss (Wagen Rücklauf) oder (beginnend mit Version 16,0) ein Kommentar gefolgt von einem Wagen Rücklauf eingefügt werden.

  > [!NOTE]
  > Wenn Sie das Zeilen Fortsetzungs Zeichen weglassen, wird der Visual Basic-Compiler in einigen Fällen implizit die Anweisung in der nächsten Codezeile fortsetzen. Eine Liste der Syntax Elemente, für die Sie das Zeilen Fortsetzungs Zeichen weglassen können, finden Sie unter "implizite Zeilen Fortsetzung" in- [Anweisungen](../language-features/statements.md).

  Im folgenden Beispiel wird die-Anweisung in vier Zeilen aufgeteilt, wobei Zeilen Fortsetzungs Zeichen alle außer der letzten Zeile beenden.

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  Wenn Sie diese Sequenz verwenden, wird der Code leichter lesbar, sowohl online als auch gedruckt.

  Das Zeilen Fortsetzungs Zeichen muss das letzte Zeichen in einer Zeile sein. Sie können das Element nicht in derselben Zeile verfolgen.

  Es gibt einige Einschränkungen, bei denen Sie das Zeilen Fortsetzungs Zeichen verwenden können. Sie können Sie z. b. nicht in der Mitte eines Argument namens verwenden. Sie können eine Argumentliste mit dem Zeilen Fortsetzungs Zeichen unterbrechen, aber die einzelnen Namen der Argumente müssen unverändert bleiben.

  Sie können einen Kommentar nicht fortsetzen, indem Sie ein Zeilen Fortsetzungs Zeichen verwenden. Der Compiler untersucht die Zeichen in einem Kommentar nicht auf eine besondere Bedeutung. Wiederholen Sie für einen mehrzeiligen Kommentar das Kommentar Symbol ( `'` ) in jeder Zeile.

 Obwohl das platzieren jeder Anweisung in einer separaten Zeile die empfohlene Methode ist, können Visual Basic auch mehrere-Anweisungen in derselben Zeile platzieren.

## <a name="to-place-multiple-statements-on-the-same-line"></a>So platzieren Sie mehrere Anweisungen in derselben Zeile

Trennen Sie die-Anweisungen mit einem Doppelpunkt ( `:` ), wie im folgenden Beispiel gezeigt:

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a>Weitere Informationen

- [Programmstruktur und Codekonventionen](program-structure-and-code-conventions.md)
- [Anweisungen](../language-features/statements.md)
