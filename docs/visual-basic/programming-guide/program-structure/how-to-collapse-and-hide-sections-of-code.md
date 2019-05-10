---
title: 'Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 367527fd638f6855077caf8ff5911edb333dfcbf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648767"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="ea8bb-102">Vorgehensweise: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea8bb-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>
<span data-ttu-id="ea8bb-103">Die `#Region` Richtlinie ermöglicht es Ihnen, reduzieren und Ausblenden von Codeabschnitten in Visual Basic-Dateien.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="ea8bb-104">Die `#Region` -Direktive können Sie einen Block mit Code, den Sie erweitern können, oder reduzieren angeben, wenn Sie Visual Studio Code-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="ea8bb-105">Die Möglichkeit, um ausgewählten Code auszublenden, kann Ihre Dateien leichter lesbar und besser verwaltbar.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="ea8bb-106">Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="ea8bb-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>  
  
 <span data-ttu-id="ea8bb-107">`#Region` Direktiven unterstützen Code blockieren Semantik, wie z. B. `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="ea8bb-108">Dies bedeutet, dass sie nicht in einem Block beginnen und enden in einem anderen; die Start- und Endzeit müssen im selben Block sein.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="ea8bb-109">`#Region` Anweisungen sind innerhalb von Funktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-109">`#Region` directives are not supported within functions.</span></span>  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="ea8bb-110">Reduzieren und Ausblenden eines Abschnitts des Codes</span><span class="sxs-lookup"><span data-stu-id="ea8bb-110">To collapse and hide a section of code</span></span>  
  
- <span data-ttu-id="ea8bb-111">Platzieren Sie den Abschnitt des Codes zwischen der `#Region` und `#End Region` -Anweisungen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ea8bb-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]  
  
     <span data-ttu-id="ea8bb-112">Die `#Region` Block kann mehrere Male in einer Codedatei verwendet werden; daher können Benutzer ihre eigenen Blöcke von Prozeduren und Klassen, die wiederum reduziert werden können, definieren.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="ea8bb-113">`#Region` Blöcke können auch in anderen geschachtelt werden `#Region` Blöcke.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea8bb-114">Ausblenden von Code verhindert nicht, dass er kompiliert wird, und hat keinen Einfluss auf `#If...#End If` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ea8bb-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8bb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea8bb-115">See also</span></span>

- [<span data-ttu-id="ea8bb-116">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="ea8bb-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="ea8bb-117">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ea8bb-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="ea8bb-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ea8bb-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="ea8bb-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="ea8bb-119">Outlining</span></span>](/visualstudio/ide/outlining)
