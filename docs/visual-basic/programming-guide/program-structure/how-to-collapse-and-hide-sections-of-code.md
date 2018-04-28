---
title: 'Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4497c9586182cca9e2be97dc39e5ccb242725d25
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="6005e-102">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6005e-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="6005e-103">Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und blenden Sie Codeabschnitte im Visual Basic-Dateien.</span><span class="sxs-lookup"><span data-stu-id="6005e-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="6005e-104">Die `#Region` Richtlinie ermöglicht die Angabe einen Block mit Code, den Sie erweitern können oder reduzieren bei Verwendung von Visual Studio Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="6005e-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="6005e-105">Die Möglichkeit, um ausgewählten Code auszublenden, sind die Dateien, besser verwaltbare und einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="6005e-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="6005e-106">Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="6005e-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="6005e-107">`#Region` Direktiven unterstützen Codesemantik-Block, wie z. B. `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="6005e-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="6005e-108">Dies bedeutet, dass sie nicht in einem Block beginnen und enden in einer anderen; Anfang und Ende müssen im selben Block sein.</span><span class="sxs-lookup"><span data-stu-id="6005e-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="6005e-109">`#Region` Richtlinien werden nicht innerhalb von Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6005e-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="6005e-110">Reduzieren und Ausblenden von einem Abschnitt des Codes</span><span class="sxs-lookup"><span data-stu-id="6005e-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="6005e-111">Platzieren Sie den Codeabschnitt zwischen den `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6005e-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="6005e-112">Die `#Region` Block kann mehrmals verwendet werden, in einer Codedatei; Folglich können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren.</span><span class="sxs-lookup"><span data-stu-id="6005e-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="6005e-113">`#Region` Blöcke können auch geschachtelt werden, in anderen `#Region` blockiert.</span><span class="sxs-lookup"><span data-stu-id="6005e-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6005e-114">Ausblenden von Code verhindert nicht, dass sie kompiliert wird, und hat keinen Einfluss auf `#If...#End If` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6005e-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6005e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6005e-115">See Also</span></span>  
 [<span data-ttu-id="6005e-116">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="6005e-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="6005e-117">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6005e-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="6005e-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="6005e-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="6005e-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="6005e-119">Outlining</span></span>](/visualstudio/ide/outlining)
