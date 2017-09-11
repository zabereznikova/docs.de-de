---
title: 'Gewusst wie: reduzieren und Ausblenden von Codeabschnitten (Visual Basic) | Microsoft-Dokumentation'
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
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
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
ms.openlocfilehash: 4dcd5cd5d79629fd008534112cb72d5bcfec476e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="75bfe-102">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75bfe-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="75bfe-103">Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und Ausblenden von Codeabschnitten im [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien.</span><span class="sxs-lookup"><span data-stu-id="75bfe-103">The `#Region` directive enables you to collapse and hide sections of code in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files.</span></span> <span data-ttu-id="75bfe-104">Die `#Region` -Direktive können Sie einen Codeblock, den Sie erweitern können oder reduzieren angeben, bei Verwendung der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="75bfe-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] code editor.</span></span> <span data-ttu-id="75bfe-105">Die Möglichkeit, ausgewählte Codeabschnitte auszublenden macht Ihre Dateien verwaltet werden und sind einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="75bfe-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="75bfe-106">Weitere Informationen finden Sie unter [Gliederung](https://docs.microsoft.com/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="75bfe-106">For more information, see [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="75bfe-107">`#Region`Direktiven unterstützen Codesemantik Block, wie z. B. `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="75bfe-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="75bfe-108">Das heißt, sie können nicht in einem Block beginnen und enden in einer anderen. Anfang und Ende müssen im selben Block sein.</span><span class="sxs-lookup"><span data-stu-id="75bfe-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="75bfe-109">`#Region`-Direktiven werden in Funktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75bfe-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="75bfe-110">Reduzieren und Ausblenden eines Abschnitts des Codes</span><span class="sxs-lookup"><span data-stu-id="75bfe-110">To collapse and hide a section of code</span></span>  
  
-   <span data-ttu-id="75bfe-111">Platzieren Sie den Codeabschnitt zwischen die `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75bfe-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     <span data-ttu-id="75bfe-112">[!code-vb[VbVbalrConditionalComp&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75bfe-112">[!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]</span></span>  
  
     <span data-ttu-id="75bfe-113">Die `#Region` Block kann mehrmals in einer Codedatei verwendet werden, daher können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren.</span><span class="sxs-lookup"><span data-stu-id="75bfe-113">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="75bfe-114">`#Region`Blöcke können auch geschachtelt werden, in den anderen `#Region` blockiert.</span><span class="sxs-lookup"><span data-stu-id="75bfe-114">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75bfe-115">Ausblenden von Code verhindert nicht, dass er kompiliert und hat keinen Einfluss auf `#If...#End If` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="75bfe-115">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bfe-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75bfe-116">See Also</span></span>  
 <span data-ttu-id="75bfe-117">[Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="75bfe-117">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<span data-ttu-id="75bfe-118"> [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="75bfe-118"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="75bfe-119"> [#If... Then... #Else-Direktive](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="75bfe-119"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="75bfe-120"> [Gliedern](https://docs.microsoft.com/visualstudio/ide/outlining)</span><span class="sxs-lookup"><span data-stu-id="75bfe-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining)</span></span>
