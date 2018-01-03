---
title: "Abrufen von unterstützten Steuerelementmustern für Benutzeroberflächenautomatisierung"
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
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: "10"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 26cdf2dea8ec924d4345c1591be8fee1ed489c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="517fc-102">Abrufen von unterstützten Steuerelementmustern für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="517fc-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="517fc-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="517fc-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="517fc-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="517fc-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="517fc-105">In diesem Thema wird gezeigt, wie Steuerelementmusterobjekte aus abzurufenden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente.</span><span class="sxs-lookup"><span data-stu-id="517fc-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="517fc-106">Abrufen aller Steuerelementmuster</span><span class="sxs-lookup"><span data-stu-id="517fc-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="517fc-107">Abrufen der <xref:System.Windows.Automation.AutomationElement> , an dessen Steuerelementmustern Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="517fc-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="517fc-108">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> um alle Steuerelementmuster aus dem Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="517fc-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="517fc-109">Es wird dringend empfohlen, dass ein Client nicht verwenden <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="517fc-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="517fc-110">Leistung kann schwerwiegend beeinträchtigt werden, wie diese Methode ruft <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> intern für jedes vorhandene Steuerelementmuster.</span><span class="sxs-lookup"><span data-stu-id="517fc-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="517fc-111">Wenn möglich sollte ein Client Aufrufen <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> für die gewünschten Steuerelementmuster.</span><span class="sxs-lookup"><span data-stu-id="517fc-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="517fc-112">Abrufen eines bestimmten Steuerelementmusters</span><span class="sxs-lookup"><span data-stu-id="517fc-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="517fc-113">Abrufen der <xref:System.Windows.Automation.AutomationElement> , an dessen Steuerelementmustern Sie interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="517fc-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="517fc-114">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> auf ein bestimmtes Muster abzufragen.</span><span class="sxs-lookup"><span data-stu-id="517fc-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="517fc-115">Diese Methoden ähneln sich, wenn das Muster nicht gefunden wird, aber <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> löst eine Ausnahme aus und <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> gibt `false`.</span><span class="sxs-lookup"><span data-stu-id="517fc-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="517fc-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="517fc-116">Example</span></span>  
 <span data-ttu-id="517fc-117">Das folgende Beispiel ruft eine <xref:System.Windows.Automation.AutomationElement> für ein Listenelement und erhält eine <xref:System.Windows.Automation.SelectionItemPattern> aus diesem Element.</span><span class="sxs-lookup"><span data-stu-id="517fc-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="517fc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="517fc-118">See Also</span></span>  
 [<span data-ttu-id="517fc-119">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="517fc-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
