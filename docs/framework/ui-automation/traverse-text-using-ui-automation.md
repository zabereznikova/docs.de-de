---
title: "Durchlaufen von Text mit Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5b3d08c0a6293b6621d9b6debfa4d63c8abaf3d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="00bb0-102">Durchlaufen von Text mit Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="00bb0-102">Traverse Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="00bb0-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="00bb0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="00bb0-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="00bb0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="00bb0-105">In diesem Thema wird die Verwendung der [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Durchlaufen des Textinhalts eines Dokuments durch <xref:System.Windows.Automation.Text.TextUnit> -Inkremente veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="00bb0-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00bb0-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00bb0-106">Example</span></span>  
 <span data-ttu-id="00bb0-107">Im folgenden Codebeispiel wird gezeigt, wie der Inhalt eines Benutzeroberflächenautomatisierungs-Textanbieters durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="00bb0-107">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="00bb0-108">Die <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> -Methode verschiebt die <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> - und <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> -Endpunkte eines <xref:System.Windows.Automation.Text.TextPatternRange>.</span><span class="sxs-lookup"><span data-stu-id="00bb0-108">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="00bb0-109">Dieser Textbereich ist üblicherweise ein degenerierter Bereich, der die Einfügemarke darstellt.</span><span class="sxs-lookup"><span data-stu-id="00bb0-109">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00bb0-110">Da nur textbasierte eingebettete Objekte als Teil des Textstreams betrachtet werden, haben eingebettete Objekte keine Auswirkung auf `Move` oder dessen Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="00bb0-110">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="00bb0-111">Jede Methode, die <xref:System.Windows.Automation.Text.TextUnit> verwendet, wird bis zur nächstgrößeren unterstützten <xref:System.Windows.Automation.Text.TextUnit> zurückgestellt, wenn die angegebene <xref:System.Windows.Automation.Text.TextUnit> vom Steuerelement nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="00bb0-111">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00bb0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00bb0-112">See Also</span></span>  
 [<span data-ttu-id="00bb0-113">Übersicht über TextPattern für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="00bb0-113">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="00bb0-114">Hinzufügen von Inhalt zu einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="00bb0-114">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="00bb0-115">Suchen und Hervorheben von Text mit Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="00bb0-115">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [<span data-ttu-id="00bb0-116">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="00bb0-116">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="00bb0-117">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="00bb0-117">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
