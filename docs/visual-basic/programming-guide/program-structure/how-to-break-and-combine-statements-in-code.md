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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ca281035a0bd81a9b52cdd60f2bc59724852709
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="c5556-102">Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5556-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="c5556-103">Beim Schreiben von Code können Sie manchmal lange Anweisungen erstellen, die einer horizontalen Bildlauf im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="c5556-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="c5556-104">Obwohl dies Einfluss auf die keine Ausführung von Code, erschwert für Sie oder andere Personen zum Lesen des Codes, wie er auf dem Bildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c5556-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="c5556-105">In solchen Fällen sollten Sie erwägen, die lange Anweisung in mehrere Zeilen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="c5556-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="c5556-106">Eine einzelne Anweisung in mehrere Zeilen aufgeteilt</span><span class="sxs-lookup"><span data-stu-id="c5556-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="c5556-107">Verwenden Sie das Zeilenfortsetzungszeichen, wird ein Unterstrich (`_`), an dem Punkt, an dem die Zeile umbrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5556-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="c5556-108">Dem Unterstrich muss ein Leerzeichen direkt vorangestellt und ein Zeilenabschlusszeichen (Wagenrücklauf) direkt nachgestellt sein.</span><span class="sxs-lookup"><span data-stu-id="c5556-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5556-109">In einigen Fällen Wenn Sie das Zeilenfortsetzungszeichen weglassen wird Visual Basic-Compiler implizit die Anweisung in der nächsten Zeile des Codes fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="c5556-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="c5556-110">Eine Liste der Elemente der Syntax für die Sie das Zeilenfortsetzungszeichen weglassen können, finden Sie unter "Implizite Zeilenfortsetzung" in [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="c5556-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="c5556-111">Im folgenden Beispiel wird die Anweisung in vier Zeilen mit Zeilenfortsetzungszeichen beendet alle jedoch die letzte Zeile aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="c5556-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     <span data-ttu-id="c5556-112">[!code-vb[VbVbcnConventions&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c5556-112">[!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span></span>  
  
     <span data-ttu-id="c5556-113">Mit dieser Sequenz wird der Code einfacher zu lesen, sowohl online als auch gedruckt.</span><span class="sxs-lookup"><span data-stu-id="c5556-113">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="c5556-114">Das Zeilenfortsetzungszeichen muss das letzte Zeichen in einer Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="c5556-114">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="c5556-115">Sie können nicht es mit etwas anderes in derselben Zeile folgen.</span><span class="sxs-lookup"><span data-stu-id="c5556-115">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="c5556-116">Einige Einschränkungen vorhanden, wo Sie das Zeilenfortsetzungszeichen verwenden können. Beispielsweise kann nicht in der Mitte ein Argumentname Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c5556-116">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="c5556-117">Sie können eine Argumentliste mit dem Zeilenfortsetzungszeichen unterbrechen, aber die einzelnen Argumente müssen intakt bleiben.</span><span class="sxs-lookup"><span data-stu-id="c5556-117">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="c5556-118">Einen Kommentar kann nicht fortgesetzt werden, mit einem Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="c5556-118">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="c5556-119">Der Compiler untersuchen nicht die Zeichen in einem Kommentar für besondere Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="c5556-119">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="c5556-120">Für einen mehrzeiligen Kommentar, wiederholen Sie das Kommentarsymbol (`'`) in jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="c5556-120">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="c5556-121">Zwar wird empfohlen, jede Anweisung in einer separaten Zeile platzieren [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] darüber hinaus können Sie mehrere Anweisungen in der gleichen Zeile platzieren.</span><span class="sxs-lookup"><span data-stu-id="c5556-121">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="c5556-122">Um mehrere Anweisungen in der gleichen Zeile platzieren</span><span class="sxs-lookup"><span data-stu-id="c5556-122">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="c5556-123">Trennen Sie die Anweisungen mit einem Doppelpunkt (`:`), wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c5556-123">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     <span data-ttu-id="c5556-124">[!code-vb[VbVbcnConventions&#10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c5556-124">[!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5556-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5556-125">See Also</span></span>  
 <span data-ttu-id="c5556-126">[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="c5556-126">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="c5556-127"> [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="c5556-127"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>
