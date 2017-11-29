---
title: Kommentare in Code (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Uncomment button
- REM statement [Visual Basic]
- comments [Visual Basic], in code
- comments [Visual Basic], Visual Basic code
- Comment button
- buttons [Visual Basic], Uncomment
- buttons [Visual Basic], Comment
- code comments [Visual Basic], Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cf1aa755c479c73c64951f80ab0b76985507da6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="63f80-102">Kommentare in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63f80-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="63f80-103">Wenn Sie die Codebeispiele lesen, werden Sie oft auf das Kommentarsymbol (`'`) stoßen.</span><span class="sxs-lookup"><span data-stu-id="63f80-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="63f80-104">Dieses Symbol weist den [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler ignoriert den folgenden Text oder die *Kommentar*.</span><span class="sxs-lookup"><span data-stu-id="63f80-104">This symbol tells the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="63f80-105">Kommentare sind kurze, erläuternde Hinweise, die dem Code zum Zwecke der besseren Verständlichkeit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="63f80-106">Es gilt als guter Programmierstil, alle Prozeduren mit einem kurzen Kommentar zu beginnen, der die Funktionsmerkmale der Prozedur (ihre Aufgabe) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="63f80-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="63f80-107">Dies ist zu Ihrem eigenen Nutzen und zum Nutzen jeder anderen Person, die den Code liest.</span><span class="sxs-lookup"><span data-stu-id="63f80-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="63f80-108">Dabei ist es sinnvoll, die Einzelheiten der Implementierung, d. h., wie die Prozedur funktioniert, von den Kommentaren abzugrenzen, in denen die funktionalen Eigenschaften beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="63f80-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="63f80-109">Falls Sie in einem Kommentar Einzelheiten der Implementierung beschreiben, denken Sie daran, diese entsprechend zu aktualisieren, wenn Sie die Funktion ändern.</span><span class="sxs-lookup"><span data-stu-id="63f80-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="63f80-110">Kommentare können nach einer Anweisung in der gleichen Zeile eingefügt werden oder eine ganze Zeile belegen.</span><span class="sxs-lookup"><span data-stu-id="63f80-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="63f80-111">Beide Fälle werden im folgenden Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="63f80-111">Both are illustrated in the following code.</span></span>  
  
 [!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]  
  
 <span data-ttu-id="63f80-112">Wenn der Kommentar mehr als eine Zeile beansprucht, verwenden Sie das Kommentarsymbol in jeder neuen Zeile, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="63f80-112">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="63f80-113">Richtlinien für Kommentare</span><span class="sxs-lookup"><span data-stu-id="63f80-113">Commenting Guidelines</span></span>  
 <span data-ttu-id="63f80-114">Die folgende Tabelle enthält allgemeine Richtlinien für die verschiedenen Arten von Kommentaren, die einem Codeabschnitt vorangestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="63f80-114">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="63f80-115">Diese Richtlinien sind als Empfehlungen gedacht, da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keine Regeln für das Hinzufügen von Kommentaren erzwingt.</span><span class="sxs-lookup"><span data-stu-id="63f80-115">These are suggestions; [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not enforce rules for adding comments.</span></span> <span data-ttu-id="63f80-116">Wenden Sie diese Empfehlungen so an, wie sie für Sie und andere Leser am sinnvollsten sind.</span><span class="sxs-lookup"><span data-stu-id="63f80-116">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="63f80-117">Kommentartyp</span><span class="sxs-lookup"><span data-stu-id="63f80-117">Comment type</span></span>|<span data-ttu-id="63f80-118">Kommentarbeschreibung</span><span class="sxs-lookup"><span data-stu-id="63f80-118">Comment description</span></span>|  
|<span data-ttu-id="63f80-119">Zweck</span><span class="sxs-lookup"><span data-stu-id="63f80-119">Purpose</span></span>|<span data-ttu-id="63f80-120">Hier wird beschrieben, was die Prozedur bewirkt (nicht, wie sie dies bewirkt).</span><span class="sxs-lookup"><span data-stu-id="63f80-120">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="63f80-121">Annahmen</span><span class="sxs-lookup"><span data-stu-id="63f80-121">Assumptions</span></span>|<span data-ttu-id="63f80-122">Listet alle externen Variablen, Steuerelemente, offenen Dateien und andere Elemente auf, auf die die Prozedur zugreift.</span><span class="sxs-lookup"><span data-stu-id="63f80-122">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="63f80-123">Effekte</span><span class="sxs-lookup"><span data-stu-id="63f80-123">Effects</span></span>|<span data-ttu-id="63f80-124">Hier werden die einzelnen betroffenen externen Variablen, Steuerelemente oder Dateien sowie deren Auswirkungen genannt (falls dies nicht offensichtlich ist).</span><span class="sxs-lookup"><span data-stu-id="63f80-124">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="63f80-125">Eingaben</span><span class="sxs-lookup"><span data-stu-id="63f80-125">Inputs</span></span>|<span data-ttu-id="63f80-126">Gibt den Zweck des Arguments an.</span><span class="sxs-lookup"><span data-stu-id="63f80-126">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="63f80-127">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="63f80-127">Returns</span></span>|<span data-ttu-id="63f80-128">Erläutert die von der Prozedur zurückgegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="63f80-128">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="63f80-129">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63f80-129">Remember the following points:</span></span>  
  
-   <span data-ttu-id="63f80-130">Vor jeder wichtigen Variablendeklaration sollte ein Kommentar stehen, der Sinn und Zweck der deklarierten Variablen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="63f80-130">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
-   <span data-ttu-id="63f80-131">Variablen, Steuerelemente und Prozeduren sollten so klar benannt werden, dass Kommentare nur für komplexe Implementierungsdetails erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="63f80-131">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
-   <span data-ttu-id="63f80-132">Auf eine Zeilenfortsetzungszeichenfolge darf nicht in der gleichen Zeile ein Kommentar folgen.</span><span class="sxs-lookup"><span data-stu-id="63f80-132">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="63f80-133">Sie können hinzufügen oder entfernen Sie Kommentarsymbole für einen Codeblock, indem Sie eine oder mehrere Codezeilen markieren und die **Kommentar** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "VaCommentButton ")) und **entfernen Sie den Kommentar** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "VaUncommentButton")) Schaltflächen auf der **bearbeiten**  Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="63f80-133">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) and **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63f80-134">Sie können Code auch Kommentare hinzufügen, indem Sie vor dem betreffenden Text das `REM`-Schlüsselwort einfügen.</span><span class="sxs-lookup"><span data-stu-id="63f80-134">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="63f80-135">Allerdings die `'` Symbol und die **Kommentar**/**Auswahlkommentar löschen** Schaltflächen sind einfacher zu verwenden und beanspruchen weniger Speicherplatz und Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="63f80-135">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f80-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63f80-136">See Also</span></span>  
 [<span data-ttu-id="63f80-137">Dokumentieren von Code mit XML-Kommentare</span><span class="sxs-lookup"><span data-stu-id="63f80-137">Documenting Your Code With XML Comments</span></span>](http://msdn.microsoft.com/magazine/dd722812.aspx)  
 [<span data-ttu-id="63f80-138">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="63f80-138">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="63f80-139">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="63f80-139">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="63f80-140">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="63f80-140">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="63f80-141">REM-Anweisung</span><span class="sxs-lookup"><span data-stu-id="63f80-141">REM Statement</span></span>](../../../visual-basic/language-reference/statements/rem-statement.md)
