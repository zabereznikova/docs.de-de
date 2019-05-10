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
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="6c393-102">Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c393-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="6c393-103">Wenn Ihr Code schreiben, können Sie gelegentlich lange Anweisungen erstellen, die erfordern, horizontalen Bildlauf im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="6c393-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="6c393-104">Obwohl dies Einfluss auf die nicht Ihr Code ausgeführt wird, erleichtert es schwierig für Sie oder andere Personen Lesen des Codes, wie er auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6c393-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="6c393-105">In solchen Fällen sollten Sie erwägen, die lange Anweisung in mehrere Zeilen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="6c393-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="6c393-106">Eine einzelne Anweisung in mehrere Zeilen aufteilen</span><span class="sxs-lookup"><span data-stu-id="6c393-106">To break a single statement into multiple lines</span></span>  
  
- <span data-ttu-id="6c393-107">Verwenden Sie das Zeilenfortsetzungszeichen, wird ein Unterstrich (`_`), an dem Punkt, an dem die Zeile umbrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c393-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="6c393-108">Dem Unterstrich muss ein Leerzeichen direkt vorangestellt und ein Zeilenabschlusszeichen (Wagenrücklauf) direkt nachgestellt sein.</span><span class="sxs-lookup"><span data-stu-id="6c393-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6c393-109">In einigen Fällen Wenn Sie das Zeilenfortsetzungszeichen weglassen wird Visual Basic-Compiler implizit die Anweisung in der nächsten Zeile des Codes fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6c393-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="6c393-110">Eine Liste der Syntaxelemente, die für die Sie dem Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="6c393-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="6c393-111">Im folgenden Beispiel wird die Anweisung in vier Zeilen mit Zeilenfortsetzungszeichen beendet alle jedoch die letzte Zeile aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="6c393-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="6c393-112">Verwenden diese Sequenz wird Ihr Code einfacher zu lesen, sowohl online als auch gedruckt.</span><span class="sxs-lookup"><span data-stu-id="6c393-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="6c393-113">Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="6c393-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="6c393-114">Sie können nicht es mit anderen Elementen in der gleichen Zeile folgen.</span><span class="sxs-lookup"><span data-stu-id="6c393-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="6c393-115">Einige Einschränkungen vorhanden, wo Sie das Zeilenfortsetzungszeichen verwenden können. Beispielsweise kann nicht in der Mitte ein Argumentname Verwendung.</span><span class="sxs-lookup"><span data-stu-id="6c393-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="6c393-116">Sie können eine Argumentliste, mit dem Zeilenfortsetzungszeichen unterbrechen, aber die einzelnen Argumente müssen intakt bleiben.</span><span class="sxs-lookup"><span data-stu-id="6c393-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="6c393-117">Einen Kommentar kann nicht fortgesetzt werden, mithilfe einer Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="6c393-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="6c393-118">Der Compiler überprüfen nicht Sie die Zeichen in einen Kommentar für eine besondere Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="6c393-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="6c393-119">Für einen mehrzeiligen Kommentar, wiederholen Sie das Kommentarsymbol (`'`) in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="6c393-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="6c393-120">Obwohl jede Anweisung in einer eigenen Zeile platzieren die empfohlene Methode ist, ermöglicht Visual Basic auch Sie mehrere Anweisungen in der gleichen Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="6c393-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="6c393-121">Mehrere Anweisungen in der gleichen Zeile platzieren</span><span class="sxs-lookup"><span data-stu-id="6c393-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="6c393-122">Trennen Sie die Anweisungen durch einen Doppelpunkt (`:`), wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6c393-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="6c393-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c393-123">See also</span></span>

- [<span data-ttu-id="6c393-124">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="6c393-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="6c393-125">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="6c393-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
