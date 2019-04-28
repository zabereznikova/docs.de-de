---
title: 'Vorgehensweise: Anpassen des Abstands zwischen Absätzen'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777012"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="8aa40-102">Vorgehensweise: Anpassen des Abstands zwischen Absätzen</span><span class="sxs-lookup"><span data-stu-id="8aa40-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="8aa40-103">Dieses Beispiel zeigt, wie zum Anpassen oder Entfernen des Abstands zwischen Absätzen in fortlaufendem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="8aa40-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="8aa40-104">In einem fortlaufenden Inhalt ist zusätzlichen Abstands zwischen Absätzen das Ergebnis der Ränder, legen Sie für diese Absätze; Daher kann der Abstand zwischen Absätzen gesteuert werden, durch Anpassen der Ränder auf den Absätzen.</span><span class="sxs-lookup"><span data-stu-id="8aa40-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="8aa40-105">Um einen zusätzlichen Abstand zwischen den beiden Absätze tauschen vollständig zu vermeiden, legen Sie die Ränder für die Absätze **0**.</span><span class="sxs-lookup"><span data-stu-id="8aa40-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="8aa40-106">Einheitliche Abstands zwischen Absätzen während einer gesamten erreichen <xref:System.Windows.Documents.FlowDocument>, verwenden Sie Formatierung, um für alle Absätze im ein einheitlicher Rand fest der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="8aa40-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="8aa40-107">Es ist wichtig zu beachten, dass die Ränder für zwei angrenzende Absätze "reduzieren" werden der größere der beiden Ränder anstatt verdoppelt werden.</span><span class="sxs-lookup"><span data-stu-id="8aa40-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="8aa40-108">Wenn zwei angrenzende Absätze bzw. Ränder 20 Pixel und 40 Pixel haben, ist der resultierende Abstand zwischen den Abschnitten also 40 Pixel, die größere der beiden Randwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8aa40-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aa40-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8aa40-109">Example</span></span>  
 <span data-ttu-id="8aa40-110">Im folgenden Beispiel wird die Formatierung auf den Rand für alle festzulegen <xref:System.Windows.Documents.Paragraph> Elemente in einem <xref:System.Windows.Documents.FlowDocument> zu **0**, wodurch effektiv entfällt zusätzlichen Abstand zwischen Absätzen in die <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="8aa40-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
