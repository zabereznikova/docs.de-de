---
title: 'Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: f6c272b7ac016258d99873512cb789bba6739727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650854"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="422c1-102">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="422c1-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="422c1-103">Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und blenden Sie Codeabschnitte im Visual Basic-Dateien.</span><span class="sxs-lookup"><span data-stu-id="422c1-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="422c1-104">Die `#Region` Richtlinie ermöglicht die Angabe einen Block mit Code, den Sie erweitern können oder reduzieren bei Verwendung von Visual Studio Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="422c1-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="422c1-105">Die Möglichkeit, um ausgewählten Code auszublenden, sind die Dateien, besser verwaltbare und einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="422c1-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="422c1-106">Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="422c1-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="422c1-107">`#Region` Direktiven unterstützen Codesemantik-Block, wie z. B. `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="422c1-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="422c1-108">Dies bedeutet, dass sie nicht in einem Block beginnen und enden in einer anderen; Anfang und Ende müssen im selben Block sein.</span><span class="sxs-lookup"><span data-stu-id="422c1-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="422c1-109">`#Region` Richtlinien werden nicht innerhalb von Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="422c1-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="422c1-110">Reduzieren und Ausblenden von einem Abschnitt des Codes</span><span class="sxs-lookup"><span data-stu-id="422c1-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="422c1-111">Platzieren Sie den Codeabschnitt zwischen den `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="422c1-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     <span data-ttu-id="422c1-112">Die `#Region` Block kann mehrmals verwendet werden, in einer Codedatei; Folglich können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren.</span><span class="sxs-lookup"><span data-stu-id="422c1-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="422c1-113">`#Region` Blöcke können auch geschachtelt werden, in anderen `#Region` blockiert.</span><span class="sxs-lookup"><span data-stu-id="422c1-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="422c1-114">Ausblenden von Code verhindert nicht, dass sie kompiliert wird, und hat keinen Einfluss auf `#If...#End If` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="422c1-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422c1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="422c1-115">See Also</span></span>  
 [<span data-ttu-id="422c1-116">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="422c1-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="422c1-117">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="422c1-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="422c1-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="422c1-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="422c1-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="422c1-119">Outlining</span></span>](/visualstudio/ide/outlining)
