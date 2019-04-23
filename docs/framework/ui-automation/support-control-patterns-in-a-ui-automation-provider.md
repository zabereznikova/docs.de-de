---
title: Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 65ec0f85bf0a63d0051ff9491623a65abee7a05c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336680"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="51673-102">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="51673-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="51673-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="51673-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="51673-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="51673-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="51673-105">In diesem Thema wird erläutert, wie Sie ein oder mehrere Steuerelementmuster in einem Benutzeroberflächenautomatisierungs-Anbieter implementieren, damit Clientanwendungen Steuerelemente ändern und Daten von Steuerelementen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="51673-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="51673-106">Unterstützung von Steuerelementmustern</span><span class="sxs-lookup"><span data-stu-id="51673-106">Support Control Patterns</span></span>  
  
1. <span data-ttu-id="51673-107">Implementieren Sie die entsprechenden Schnittstellen für die Steuerelementmuster, die vom Element unterstützt werden sollen, z. B. <xref:System.Windows.Automation.Provider.IInvokeProvider> für <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="51673-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2. <span data-ttu-id="51673-108">Geben Sie das Objekt, das die Implementierung der einzelnen Steuerelementschnittstellen enthält, in der Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType>zurück</span><span class="sxs-lookup"><span data-stu-id="51673-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="51673-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51673-109">Example</span></span>  
 <span data-ttu-id="51673-110">Im folgenden Beispiel wird eine Implementierung von <xref:System.Windows.Automation.Provider.ISelectionProvider> für ein benutzerdefiniertes Einzelauswahl-Listenfeld dargestellt.</span><span class="sxs-lookup"><span data-stu-id="51673-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="51673-111">Die Implementierung gibt drei Eigenschaften zurück und ruft das aktuell ausgewählte Element ab.</span><span class="sxs-lookup"><span data-stu-id="51673-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="51673-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51673-112">Example</span></span>  
 <span data-ttu-id="51673-113">Im folgenden Beispiel wird eine Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> dargestellt, die die <xref:System.Windows.Automation.Provider.ISelectionProvider>implementierende Klasse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="51673-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="51673-114">Die meisten Listenfeld-Steuerelemente unterstützt andere Muster auch, aber in diesem Beispiel wird ein null-Verweis (`Nothing` in Microsoft Visual Basic .NET) für alle anderen Musterbezeichner zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="51673-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="51673-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51673-115">See also</span></span>

- [<span data-ttu-id="51673-116">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="51673-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- <span data-ttu-id="51673-117">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="51673-117">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)</span></span>
