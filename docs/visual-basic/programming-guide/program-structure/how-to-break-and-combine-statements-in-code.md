---
title: 'Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code'
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
ms.openlocfilehash: f1a24c001cd20acc7663fb4cbe60e7e35a9c8fc3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347429"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="d30a7-102">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d30a7-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>

<span data-ttu-id="d30a7-103">Wenn Sie Ihren Code schreiben, können Sie häufig lange Anweisungen erstellen, die den horizontalen Bildlauf im Code-Editor erfordern.</span><span class="sxs-lookup"><span data-stu-id="d30a7-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="d30a7-104">Dies wirkt sich nicht auf die Art und Weise aus, in der der Code ausgeführt wird. es ist jedoch schwierig, den Code so zu lesen, wie er auf dem Monitor angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d30a7-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="d30a7-105">In solchen Fällen sollten Sie die Unterbrechung der einzelnen langen Anweisung in mehrere Zeilen in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="d30a7-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>

## <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="d30a7-106">So brechen Sie eine einzelne Anweisung in mehrere Zeilen um</span><span class="sxs-lookup"><span data-stu-id="d30a7-106">To break a single statement into multiple lines</span></span>

<span data-ttu-id="d30a7-107">Verwenden Sie das Zeilen Fortsetzungs Zeichen, bei dem es sich um einen Unterstrich (`_`) handelt, an dem Punkt, an dem Sie die Linie unterbrechen möchten.</span><span class="sxs-lookup"><span data-stu-id="d30a7-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="d30a7-108">Dem Unterstrich muss ein Leerzeichen unmittelbar vorangestellt sein, und es muss unmittelbar ein Zeichen für den Zeilen Abschluss (Wagen Rücklauf) oder (beginnend mit Version 16,0) ein Kommentar gefolgt von einem Wagen Rücklauf eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d30a7-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return) or (starting with version 16.0) a comment followed by a carriage return.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d30a7-109">Wenn Sie das Zeilen Fortsetzungs Zeichen weglassen, wird der Visual Basic-Compiler in einigen Fällen implizit die Anweisung in der nächsten Codezeile fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="d30a7-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="d30a7-110">Eine Liste der Syntax Elemente, für die Sie das Zeilen Fortsetzungs Zeichen weglassen können, finden Sie unter "implizite Zeilen Fortsetzung" in- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="d30a7-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>

  <span data-ttu-id="d30a7-111">Im folgenden Beispiel wird die-Anweisung in vier Zeilen aufgeteilt, wobei Zeilen Fortsetzungs Zeichen alle außer der letzten Zeile beenden.</span><span class="sxs-lookup"><span data-stu-id="d30a7-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  <span data-ttu-id="d30a7-112">Wenn Sie diese Sequenz verwenden, wird der Code leichter lesbar, sowohl online als auch gedruckt.</span><span class="sxs-lookup"><span data-stu-id="d30a7-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>

  <span data-ttu-id="d30a7-113">Das Zeilen Fortsetzungs Zeichen muss das letzte Zeichen in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="d30a7-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="d30a7-114">Sie können das Element nicht in derselben Zeile verfolgen.</span><span class="sxs-lookup"><span data-stu-id="d30a7-114">You can't follow it with anything else on the same line.</span></span>

  <span data-ttu-id="d30a7-115">Es gibt einige Einschränkungen, bei denen Sie das Zeilen Fortsetzungs Zeichen verwenden können. Sie können Sie z. b. nicht in der Mitte eines Argument namens verwenden.</span><span class="sxs-lookup"><span data-stu-id="d30a7-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="d30a7-116">Sie können eine Argumentliste mit dem Zeilen Fortsetzungs Zeichen unterbrechen, aber die einzelnen Namen der Argumente müssen unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="d30a7-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>

  <span data-ttu-id="d30a7-117">Sie können einen Kommentar nicht fortsetzen, indem Sie ein Zeilen Fortsetzungs Zeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d30a7-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="d30a7-118">Der Compiler untersucht die Zeichen in einem Kommentar nicht auf eine besondere Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="d30a7-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="d30a7-119">Wenn Sie einen mehrzeiligen Kommentar haben, wiederholen Sie das Kommentar Symbol (`'`) in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="d30a7-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>

 <span data-ttu-id="d30a7-120">Obwohl das platzieren jeder Anweisung in einer separaten Zeile die empfohlene Methode ist, können Visual Basic auch mehrere-Anweisungen in derselben Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="d30a7-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>

## <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="d30a7-121">So platzieren Sie mehrere Anweisungen in derselben Zeile</span><span class="sxs-lookup"><span data-stu-id="d30a7-121">To place multiple statements on the same line</span></span>

<span data-ttu-id="d30a7-122">Trennen Sie die-Anweisungen mit einem Doppelpunkt (`:`), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d30a7-122">Separate the statements with a colon (`:`), as in the following example:</span></span>

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a><span data-ttu-id="d30a7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d30a7-123">See also</span></span>

- [<span data-ttu-id="d30a7-124">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="d30a7-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="d30a7-125">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="d30a7-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
