---
title: Kommentare in Code (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Uncomment button
- REM statement
- comments, in code
- comments, Visual Basic code
- Comment button
- buttons, Uncomment
- buttons, Comment
- code comments, Visual Basic
- Visual Basic code, comments
- comments
- code comments
ms.assetid: 90136fba-22eb-49f9-ba81-63db629b4a47
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e872c9bb67835573aadcc1016f2c6a98d434201e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="comments-in-code-visual-basic"></a><span data-ttu-id="da011-102">Kommentare in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da011-102">Comments in Code (Visual Basic)</span></span>
<span data-ttu-id="da011-103">Wenn Sie die Codebeispiele lesen, werden Sie oft auf das Kommentarsymbol (`'`) stoßen.</span><span class="sxs-lookup"><span data-stu-id="da011-103">As you read the code examples, you often encounter the comment symbol (`'`).</span></span> <span data-ttu-id="da011-104">Dieses Symbol weist den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler ignoriert den folgenden, Text oder die *Kommentar*.</span><span class="sxs-lookup"><span data-stu-id="da011-104">This symbol tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to ignore the text following it, or the *comment*.</span></span> <span data-ttu-id="da011-105">Kommentare sind kurze, erläuternde Hinweise, die dem Code zum Zwecke der besseren Verständlichkeit hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="da011-105">Comments are brief explanatory notes added to code for the benefit of those reading it.</span></span>  
  
 <span data-ttu-id="da011-106">Es gilt als guter Programmierstil, alle Prozeduren mit einem kurzen Kommentar zu beginnen, der die Funktionsmerkmale der Prozedur (ihre Aufgabe) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="da011-106">It is good programming practice to begin all procedures with a brief comment describing the functional characteristics of the procedure (what it does).</span></span> <span data-ttu-id="da011-107">Dies ist zu Ihrem eigenen Nutzen und zum Nutzen jeder anderen Person, die den Code liest.</span><span class="sxs-lookup"><span data-stu-id="da011-107">This is for your own benefit and the benefit of anyone else who examines the code.</span></span> <span data-ttu-id="da011-108">Dabei ist es sinnvoll, die Einzelheiten der Implementierung, d. h., wie die Prozedur funktioniert, von den Kommentaren abzugrenzen, in denen die funktionalen Eigenschaften beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="da011-108">You should separate the implementation details (how the procedure does it) from comments that describe the functional characteristics.</span></span> <span data-ttu-id="da011-109">Falls Sie in einem Kommentar Einzelheiten der Implementierung beschreiben, denken Sie daran, diese entsprechend zu aktualisieren, wenn Sie die Funktion ändern.</span><span class="sxs-lookup"><span data-stu-id="da011-109">When you include implementation details in the description, remember to update them when you update the function.</span></span>  
  
 <span data-ttu-id="da011-110">Kommentare können nach einer Anweisung in der gleichen Zeile eingefügt werden oder eine ganze Zeile belegen.</span><span class="sxs-lookup"><span data-stu-id="da011-110">Comments can follow a statement on the same line, or occupy an entire line.</span></span> <span data-ttu-id="da011-111">Beide Fälle werden im folgenden Code veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="da011-111">Both are illustrated in the following code.</span></span>  
  
 <span data-ttu-id="da011-112">[!code-vb[VbVbcnConventions Nr.&16;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="da011-112">[!code-vb[VbVbcnConventions#16](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="da011-113">Wenn der Kommentar mehr als eine Zeile beansprucht, verwenden Sie das Kommentarsymbol in jeder neuen Zeile, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="da011-113">If your comment requires more than one line, use the comment symbol on each line, as the following example illustrates.</span></span>  
  
 <span data-ttu-id="da011-114">[!code-vb[VbVbcnConventions&17;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="da011-114">[!code-vb[VbVbcnConventions#17](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/comments-in-code_2.vb)]</span></span>  
  
## <a name="commenting-guidelines"></a><span data-ttu-id="da011-115">Richtlinien für Kommentare</span><span class="sxs-lookup"><span data-stu-id="da011-115">Commenting Guidelines</span></span>  
 <span data-ttu-id="da011-116">Die folgende Tabelle enthält allgemeine Richtlinien für die verschiedenen Arten von Kommentaren, die einem Codeabschnitt vorangestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="da011-116">The following table provides general guidelines for what types of comments can precede a section of code.</span></span> <span data-ttu-id="da011-117">Diese Richtlinien sind als Empfehlungen gedacht, da [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keine Regeln für das Hinzufügen von Kommentaren erzwingt.</span><span class="sxs-lookup"><span data-stu-id="da011-117">These are suggestions; [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not enforce rules for adding comments.</span></span> <span data-ttu-id="da011-118">Wenden Sie diese Empfehlungen so an, wie sie für Sie und andere Leser am sinnvollsten sind.</span><span class="sxs-lookup"><span data-stu-id="da011-118">Write what works best, both for you and for anyone else who reads your code.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="da011-119">Kommentartyp</span><span class="sxs-lookup"><span data-stu-id="da011-119">Comment type</span></span>|<span data-ttu-id="da011-120">Kommentarbeschreibung</span><span class="sxs-lookup"><span data-stu-id="da011-120">Comment description</span></span>|  
|<span data-ttu-id="da011-121">Zweck</span><span class="sxs-lookup"><span data-stu-id="da011-121">Purpose</span></span>|<span data-ttu-id="da011-122">Hier wird beschrieben, was die Prozedur bewirkt (nicht, wie sie dies bewirkt).</span><span class="sxs-lookup"><span data-stu-id="da011-122">Describes what the procedure does (not how it does it)</span></span>|  
|<span data-ttu-id="da011-123">Annahmen</span><span class="sxs-lookup"><span data-stu-id="da011-123">Assumptions</span></span>|<span data-ttu-id="da011-124">Listet alle externen Variablen, Steuerelemente, offenen Dateien und andere Elemente auf, auf die die Prozedur zugreift.</span><span class="sxs-lookup"><span data-stu-id="da011-124">Lists each external variable, control, open file, or other element accessed by the procedure</span></span>|  
|<span data-ttu-id="da011-125">Effekte</span><span class="sxs-lookup"><span data-stu-id="da011-125">Effects</span></span>|<span data-ttu-id="da011-126">Hier werden die einzelnen betroffenen externen Variablen, Steuerelemente oder Dateien sowie deren Auswirkungen genannt (falls dies nicht offensichtlich ist).</span><span class="sxs-lookup"><span data-stu-id="da011-126">Lists each affected external variable, control, or file, and the effect it has (only if it is not obvious)</span></span>|  
|<span data-ttu-id="da011-127">Eingaben</span><span class="sxs-lookup"><span data-stu-id="da011-127">Inputs</span></span>|<span data-ttu-id="da011-128">Gibt den Zweck des Arguments an.</span><span class="sxs-lookup"><span data-stu-id="da011-128">Specifies the purpose of the argument</span></span>|  
|<span data-ttu-id="da011-129">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="da011-129">Returns</span></span>|<span data-ttu-id="da011-130">Erläutert die von der Prozedur zurückgegebenen Werte.</span><span class="sxs-lookup"><span data-stu-id="da011-130">Explains the values returned by the procedure</span></span>|  
  
 <span data-ttu-id="da011-131">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da011-131">Remember the following points:</span></span>  
  
-   <span data-ttu-id="da011-132">Vor jeder wichtigen Variablendeklaration sollte ein Kommentar stehen, der Sinn und Zweck der deklarierten Variablen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="da011-132">Every important variable declaration should be preceded by a comment describing the use of the variable being declared.</span></span>  
  
-   <span data-ttu-id="da011-133">Variablen, Steuerelemente und Prozeduren sollten so klar benannt werden, dass Kommentare nur für komplexe Implementierungsdetails erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="da011-133">Variables, controls, and procedures should be named clearly enough that commenting is needed only for complex implementation details.</span></span>  
  
-   <span data-ttu-id="da011-134">Auf eine Zeilenfortsetzungszeichenfolge darf nicht in der gleichen Zeile ein Kommentar folgen.</span><span class="sxs-lookup"><span data-stu-id="da011-134">Comments cannot follow a line-continuation sequence on the same line.</span></span>  
  
 <span data-ttu-id="da011-135">Können Sie hinzufügen oder Entfernen von Kommentarsymbole für einen Codeblock eine oder mehrere Codezeilen markieren und dann die **Kommentar** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "VaCommentButton")) und **Auswahlkommentar löschen** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "VaUncommentButton")) Schaltflächen auf der **bearbeiten** Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="da011-135">You can add or remove comment symbols for a block of code by selecting one or more lines of code and choosing the **Comment** (![VisualBasicWinAppCodeEditorCommentButton](../../../visual-basic/programming-guide/program-structure/media/vacommentbutton.gif "vaCommentButton")) and **Uncomment** (![VisualStudioWinAppProjectUncommentButton](../../../visual-basic/programming-guide/program-structure/media/vauncommentbutton.gif "vaUncommentButton")) buttons on the **Edit** toolbar.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da011-136">Sie können Code auch Kommentare hinzufügen, indem Sie vor dem betreffenden Text das `REM`-Schlüsselwort einfügen.</span><span class="sxs-lookup"><span data-stu-id="da011-136">You can also add comments to your code by preceding the text with the `REM` keyword.</span></span> <span data-ttu-id="da011-137">Allerdings die `'` Symbol und die **Kommentar**/**Auswahlkommentar löschen** Schaltflächen sind einfacher zu verwenden und beanspruchen weniger Platz und Speicher.</span><span class="sxs-lookup"><span data-stu-id="da011-137">However, the `'` symbol and the **Comment**/**Uncomment** buttons are easier to use and require less space and memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da011-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da011-138">See Also</span></span>  
 <span data-ttu-id="da011-139">[Dokumentieren von Code mit XML-Kommentaren](http://msdn.microsoft.com/magazine/dd722812.aspx) </span><span class="sxs-lookup"><span data-stu-id="da011-139">[Documenting Your Code With XML Comments](http://msdn.microsoft.com/magazine/dd722812.aspx) </span></span>  
<span data-ttu-id="da011-140"> [Gewusst wie: Erstellen von XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="da011-140"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md) </span></span>  
<span data-ttu-id="da011-141"> [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="da011-141"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="da011-142"> [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="da011-142"> [Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="da011-143"> [REM-Anweisung](../../../visual-basic/language-reference/statements/rem-statement.md)</span><span class="sxs-lookup"><span data-stu-id="da011-143"> [REM Statement](../../../visual-basic/language-reference/statements/rem-statement.md)</span></span>
