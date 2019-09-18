---
title: 'Vorgehensweise: Reduzieren und Ausblenden von Code Abschnitten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 4f11982cc0aa7654c1e456fb15d918a68bc4791b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054117"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="3985e-102">Vorgehensweise: Reduzieren und Ausblenden von Code Abschnitten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3985e-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="3985e-103">Die `#Region` -Direktive ermöglicht das reduzieren und Ausblenden von Code Abschnitten in Visual Basic Dateien.</span><span class="sxs-lookup"><span data-stu-id="3985e-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="3985e-104">Mit `#Region` der-Direktive können Sie einen Codeblock angeben, den Sie erweitern oder reduzieren können, wenn Sie den Visual Studio-Code-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="3985e-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="3985e-105">Durch die Möglichkeit, Code selektiv auszublenden, werden Ihre Dateien besser verwaltbar und leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="3985e-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="3985e-106">Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="3985e-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="3985e-107">`#Region`Direktiven unterstützen Code Block Semantik `#If...#End If`wie z. b.</span><span class="sxs-lookup"><span data-stu-id="3985e-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="3985e-108">Dies bedeutet, dass Sie nicht in einem Block beginnen und mit einem anderen enden können. der Start-und der Ende müssen sich im gleichen-Block befinden.</span><span class="sxs-lookup"><span data-stu-id="3985e-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="3985e-109">`#Region`-Anweisungen werden innerhalb von-Funktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3985e-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="3985e-110">So reduzieren Sie einen Code Abschnitt und blenden ihn aus</span><span class="sxs-lookup"><span data-stu-id="3985e-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="3985e-111">Platzieren Sie den Code Abschnitt zwischen der `#Region` - `#End Region` Anweisung und der-Anweisung, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3985e-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="3985e-112">Der `#Region` -Block kann mehrmals in einer Codedatei verwendet werden. Daher können Benutzer eigene Blöcke von Prozeduren und Klassen definieren, die wiederum reduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="3985e-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="3985e-113">`#Region`-Blöcke können auch in anderen `#Region` -Blöcken geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="3985e-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="3985e-114">Das Ausblenden von Code verhindert nicht, dass er kompiliert wird, und `#If...#End If` wirkt sich nicht auf-Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="3985e-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="3985e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3985e-115">See also</span></span>

- [<span data-ttu-id="3985e-116">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="3985e-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="3985e-117">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3985e-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="3985e-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="3985e-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="3985e-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="3985e-119">Outlining</span></span>](/visualstudio/ide/outlining)
