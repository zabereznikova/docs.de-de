---
title: 'Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)'
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
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="cd63d-102">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd63d-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="cd63d-103">Beim Schreiben von Code können Sie manchmal lange Anweisungen erstellen, die einer horizontalen Bildlauf im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="cd63d-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="cd63d-104">Obwohl dies Einfluss auf die nicht der Code ausgeführt wird, es erschwert es für Sie oder andere Personen, den Code zu lesen, wie er auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cd63d-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="cd63d-105">In solchen Fällen sollten Sie erwägen, die lange Anweisung in mehrere Zeilen aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="cd63d-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="cd63d-106">Zu eine einzelne Anweisung mehrere Zeilen unterbrechen</span><span class="sxs-lookup"><span data-stu-id="cd63d-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="cd63d-107">Verwenden Sie das Zeilenfortsetzungszeichen, also von einem Unterstrich (`_`), an dem Punkt, an dem Sie die Zeile umbrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd63d-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="cd63d-108">Dem Unterstrich muss ein Leerzeichen direkt vorangestellt und ein Zeilenabschlusszeichen (Wagenrücklauf) direkt nachgestellt sein.</span><span class="sxs-lookup"><span data-stu-id="cd63d-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd63d-109">In einigen Fällen Wenn Sie das Zeilenfortsetzungszeichen weglassen wird Visual Basic-Compiler implizit die Anweisung in der nächsten Zeile des Codes fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cd63d-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="cd63d-110">Eine Liste der Syntaxelemente, die für die Sie das Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="cd63d-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="cd63d-111">Im folgenden Beispiel wird die Anweisung in vier Zeilen mit Zeilenfortsetzungszeichen beendet alle jedoch die letzte Zeile aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="cd63d-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     <span data-ttu-id="cd63d-112">Diese Sequenz können Code einfacher zu lesen, sowohl online als auch gedruckt.</span><span class="sxs-lookup"><span data-stu-id="cd63d-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="cd63d-113">Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="cd63d-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="cd63d-114">Sie dürfen nicht es mit etwas anderes in derselben Zeile folgen.</span><span class="sxs-lookup"><span data-stu-id="cd63d-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="cd63d-115">Einige Einschränkungen vorhanden, wo Sie das Zeilenfortsetzungszeichen verwenden können. Beispielsweise kann nicht in der Mitte ein Argumentname Verwendung.</span><span class="sxs-lookup"><span data-stu-id="cd63d-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="cd63d-116">Sie können eine Argumentliste, mit dem Zeilenfortsetzungszeichen unterbrechen, während die individuellen Namen eines der Argumente müssen jedoch intakt bleiben.</span><span class="sxs-lookup"><span data-stu-id="cd63d-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="cd63d-117">Einen Kommentar kann nicht fortgesetzt werden, mithilfe einer Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="cd63d-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="cd63d-118">Der Compiler untersuchen nicht die Zeichen in einen Kommentar für eine besondere Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="cd63d-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="cd63d-119">Für einen mehrzeiligen Kommentar, wiederholen Sie das Kommentarsymbol (`'`) in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="cd63d-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="cd63d-120">Obwohl jede Anweisung in einer eigenen Zeile platziert die empfohlene Methode ist, ermöglicht Visual Basic außerdem mehrere Anweisungen in der gleichen Zeile platziert.</span><span class="sxs-lookup"><span data-stu-id="cd63d-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="cd63d-121">Mehrere Anweisungen in der gleichen Zeile platzieren</span><span class="sxs-lookup"><span data-stu-id="cd63d-121">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="cd63d-122">Trennen Sie die Anweisungen durch einen Doppelpunkt (`:`), wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cd63d-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cd63d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd63d-123">See Also</span></span>  
 [<span data-ttu-id="cd63d-124">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="cd63d-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="cd63d-125">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="cd63d-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
