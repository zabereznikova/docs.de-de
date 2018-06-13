---
title: 'Gewusst wie: Anpassen des Abstands zwischen Absätzen'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: b232903054cf45b70ba99a9223352391498cf79b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542947"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="5af88-102">Gewusst wie: Anpassen des Abstands zwischen Absätzen</span><span class="sxs-lookup"><span data-stu-id="5af88-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="5af88-103">Dieses Beispiel zeigt, wie anpassen oder Abstände zwischen den Absätzen in fortlaufendem Inhalt zunichte gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="5af88-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="5af88-104">In fortlaufendem Inhalt ist zusätzlicher Speicherplatz, der zwischen Absätzen angezeigt wird das Ergebnis der Ränder auf diese Absätze festgelegt; Daher kann der Abstand zwischen den Absätzen durch Anpassen der Ränder auf diesen Absätzen gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="5af88-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="5af88-105">Um einen zusätzlichen Abstand zwischen zwei Absätzen vollständig zu vermeiden, legen Sie die Seitenränder für die Absätze **0**.</span><span class="sxs-lookup"><span data-stu-id="5af88-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="5af88-106">Einheitliche Abstand zwischen den Absätzen in der gesamten eine gesamte erzielen <xref:System.Windows.Documents.FlowDocument>, mithilfe der Formatvorlage fest einen uniform Margin-Wert für alle Absätze in der <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5af88-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="5af88-107">Es ist wichtig zu beachten, dass die Ränder von zwei angrenzenden Absätzen "reduzieren" werden die größere von zwei Ränder anstatt verdoppelt werden.</span><span class="sxs-lookup"><span data-stu-id="5af88-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="5af88-108">Wenn also zwei angrenzende Absätze Ränder eines 20 Pixel und 40 Pixel aufweisen, der sich ergebenden Abstand zwischen den Absätzen 40 Pixel, das größere der beiden Randwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5af88-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5af88-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5af88-109">Example</span></span>  
 <span data-ttu-id="5af88-110">Im folgenden Beispiel wird formatieren, legen Sie den Rand für alle <xref:System.Windows.Documents.Paragraph> Elemente in einer <xref:System.Windows.Documents.FlowDocument> auf **0**, wodurch effektiv einen zusätzlichen Abstand zwischen den Absätzen in entfällt die <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="5af88-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
