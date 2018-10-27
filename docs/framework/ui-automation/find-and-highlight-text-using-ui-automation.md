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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 1a356e2872f803d393015574c380c5f99110074e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185601"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="869f0-102">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="869f0-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="869f0-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="869f0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="869f0-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="869f0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="869f0-105">In diesem Thema wird veranschaulicht, wie sequenziell suchen und markieren Sie jedes Vorkommen einer Zeichenfolge innerhalb der Inhalt eines Text-Steuerelement mit [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="869f0-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="869f0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="869f0-106">Example</span></span>  
 <span data-ttu-id="869f0-107">Im folgenden Beispiel eine <xref:System.Windows.Automation.TextPattern> Objekt aus einem Text-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="869f0-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="869f0-108">Ein <xref:System.Windows.Automation.Text.TextPatternRange> Objekt, das den Textinhalt des gesamten Dokuments darstellt wird dann erstellt mithilfe der <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> -Eigenschaft dieses <xref:System.Windows.Automation.TextPattern>.</span><span class="sxs-lookup"><span data-stu-id="869f0-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="869f0-109">Zwei zusätzliche <xref:System.Windows.Automation.Text.TextPatternRange> Objekte werden für die sequenzielle Suche erstellt und das hervorheben.</span><span class="sxs-lookup"><span data-stu-id="869f0-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="869f0-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="869f0-110">See Also</span></span>  
 [<span data-ttu-id="869f0-111">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="869f0-111">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
