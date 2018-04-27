---
title: Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
caps.latest.revision: 13
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: c66df9103b1edb43490a7e1a6a9d1a3cc87bfc28
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="6c812-102">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="6c812-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="6c812-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c812-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6c812-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="6c812-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6c812-105">In diesem Thema wird erläutert, wie Sie ein oder mehrere Steuerelementmuster in einem Benutzeroberflächenautomatisierungs-Anbieter implementieren, damit Clientanwendungen Steuerelemente ändern und Daten von Steuerelementen abrufen können.</span><span class="sxs-lookup"><span data-stu-id="6c812-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="6c812-106">Unterstützung von Steuerelementmustern</span><span class="sxs-lookup"><span data-stu-id="6c812-106">Support Control Patterns</span></span>  
  
1.  <span data-ttu-id="6c812-107">Implementieren Sie die entsprechenden Schnittstellen für die Steuerelementmuster, die vom Element unterstützt werden sollen, z. B. <xref:System.Windows.Automation.Provider.IInvokeProvider> für <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="6c812-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2.  <span data-ttu-id="6c812-108">Zurückgeben Sie das Objekt mit der Implementierung der einzelnen Steuerelementschnittstellen in der Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6c812-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="6c812-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c812-109">Example</span></span>  
 <span data-ttu-id="6c812-110">Im folgenden Beispiel wird eine Implementierung von <xref:System.Windows.Automation.Provider.ISelectionProvider> für ein benutzerdefiniertes Einzelauswahl-Listenfeld dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c812-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="6c812-111">Die Implementierung gibt drei Eigenschaften zurück und ruft das aktuell ausgewählte Element ab.</span><span class="sxs-lookup"><span data-stu-id="6c812-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="6c812-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c812-112">Example</span></span>  
 <span data-ttu-id="6c812-113">Im folgenden Beispiel wird eine Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> dargestellt, die die <xref:System.Windows.Automation.Provider.ISelectionProvider>implementierende Klasse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6c812-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="6c812-114">Die meisten Listenfeld-Steuerelemente unterstützen anderer Muster als auch, aber in diesem Beispiel wird ein null-Verweis (`Nothing` in Microsoft Visual Basic .NET).) wird für alle anderen Musterbezeichner zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c812-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in Microsoft Visual Basic .NET) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="6c812-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c812-115">See Also</span></span>  
 [<span data-ttu-id="6c812-116">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="6c812-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 <span data-ttu-id="6c812-117">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="6c812-117">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)</span></span>
