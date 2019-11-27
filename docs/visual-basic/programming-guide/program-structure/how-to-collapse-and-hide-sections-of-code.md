---
title: 'Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347410"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="da675-102">Gewusst wie: Reduzieren und Ausblenden von Codeabschnitten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da675-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="da675-103">Die `#Region`-Direktive ermöglicht das reduzieren und Ausblenden von Code Abschnitten in Visual Basic Dateien.</span><span class="sxs-lookup"><span data-stu-id="da675-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="da675-104">Mit der `#Region`-Direktive können Sie einen Codeblock angeben, den Sie erweitern oder reduzieren können, wenn Sie den Visual Studio-Code-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="da675-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="da675-105">Durch die Möglichkeit, Code selektiv auszublenden, werden Ihre Dateien besser verwaltbar und leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="da675-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="da675-106">Weitere Informationen finden Sie unter [Gliedern](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="da675-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="da675-107">`#Region` Direktiven unterstützen Code Block Semantik wie `#If...#End If`.</span><span class="sxs-lookup"><span data-stu-id="da675-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="da675-108">Dies bedeutet, dass Sie nicht in einem Block beginnen und mit einem anderen enden können. der Start-und der Ende müssen sich im gleichen-Block befinden.</span><span class="sxs-lookup"><span data-stu-id="da675-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="da675-109">`#Region`-Direktiven werden in Functions nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="da675-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="da675-110">So reduzieren Sie einen Code Abschnitt und blenden ihn aus</span><span class="sxs-lookup"><span data-stu-id="da675-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="da675-111">Platzieren Sie den Code Abschnitt zwischen den Anweisungen `#Region` und `#End Region`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="da675-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="da675-112">Der `#Region`-Block kann mehrmals in einer Codedatei verwendet werden. Daher können Benutzer eigene Blöcke von Prozeduren und Klassen definieren, die wiederum reduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="da675-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="da675-113">`#Region` Blöcke können auch innerhalb anderer `#Region` Blöcke geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="da675-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="da675-114">Das Ausblenden von Code verhindert nicht, dass er kompiliert wird, und wirkt sich nicht auf `#If...#End If`-Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="da675-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="da675-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da675-115">See also</span></span>

- [<span data-ttu-id="da675-116">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="da675-116">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="da675-117">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="da675-117">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="da675-118">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="da675-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="da675-119">Gliedern</span><span class="sxs-lookup"><span data-stu-id="da675-119">Outlining</span></span>](/visualstudio/ide/outlining)
