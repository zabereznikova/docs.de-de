---
title: 'Vorgehensweise: Programmgesteuertes Einfügen eines Elements in Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: ea9850c8490ec37032d4565c6b3375e3116d4313
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169584"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="3fa29-102">Vorgehensweise: Programmgesteuertes Einfügen eines Elements in Text</span><span class="sxs-lookup"><span data-stu-id="3fa29-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="3fa29-103">Das folgende Beispiel zeigt, wie Sie mit zwei <xref:System.Windows.Documents.TextPointer> Objekte an einen Bereich innerhalb eines Texts Anwenden einer <xref:System.Windows.Documents.Span> Element.</span><span class="sxs-lookup"><span data-stu-id="3fa29-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa29-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fa29-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="3fa29-105">In der folgenden Abbildung wird gezeigt, wie dieses Beispiel aussieht.</span><span class="sxs-lookup"><span data-stu-id="3fa29-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="3fa29-106">![Ein auf einen Textbereich angewandtes SPAN-Element](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="3fa29-106">![A Span element applied to a range of text](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa29-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fa29-107">See also</span></span>

- [<span data-ttu-id="3fa29-108">Übersicht über Flussdokumente</span><span class="sxs-lookup"><span data-stu-id="3fa29-108">Flow Document Overview</span></span>](flow-document-overview.md)
