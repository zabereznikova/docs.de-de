---
title: Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: a0df93b153f16dd09dfcc6da5d690dc69141435a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673703"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="3fb2b-102">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="3fb2b-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="3fb2b-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="3fb2b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3fb2b-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="3fb2b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3fb2b-105">In diesem Thema wird veranschaulicht, wie sequenziell suchen und markieren Sie jedes Vorkommen einer Zeichenfolge innerhalb der Inhalt eines Text-Steuerelement mit [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fb2b-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb2b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fb2b-106">Example</span></span>  
 <span data-ttu-id="3fb2b-107">Im folgenden Beispiel eine <xref:System.Windows.Automation.TextPattern> Objekt aus einem Text-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3fb2b-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="3fb2b-108">Ein <xref:System.Windows.Automation.Text.TextPatternRange> Objekt, das den Textinhalt des gesamten Dokuments darstellt wird dann erstellt mithilfe der <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> -Eigenschaft dieses <xref:System.Windows.Automation.TextPattern>.</span><span class="sxs-lookup"><span data-stu-id="3fb2b-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="3fb2b-109">Zwei zusätzliche <xref:System.Windows.Automation.Text.TextPatternRange> Objekte werden für die sequenzielle Suche erstellt und das hervorheben.</span><span class="sxs-lookup"><span data-stu-id="3fb2b-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="3fb2b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fb2b-110">See also</span></span>
- [<span data-ttu-id="3fb2b-111">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="3fb2b-111">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
