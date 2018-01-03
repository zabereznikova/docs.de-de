---
title: "Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung"
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
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f3fcbb25fab616b60a1f60d9443af13b60f2d27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="d950e-102">Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d950e-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="d950e-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d950e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d950e-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d950e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d950e-105">In diesem Thema wird gezeigt, wie zum Abrufen der Eigenschaften einer [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Element.</span><span class="sxs-lookup"><span data-stu-id="d950e-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="d950e-106">Abrufen von einem aktuellen Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="d950e-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="d950e-107">Abrufen der <xref:System.Windows.Automation.AutomationElement> , deren Eigenschaft, die Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d950e-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="d950e-108">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Current%2A> Eigenschaftsstruktur und beziehen Sie den Wert von einem seiner Member.</span><span class="sxs-lookup"><span data-stu-id="d950e-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="d950e-109">Abrufen eines zwischengespeicherten Werts</span><span class="sxs-lookup"><span data-stu-id="d950e-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="d950e-110">Abrufen der <xref:System.Windows.Automation.AutomationElement> , deren Eigenschaft, die Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d950e-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="d950e-111">Die Eigenschaft muss angegeben wurde der <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="d950e-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="d950e-112">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Cached%2A> Eigenschaftsstruktur und beziehen Sie den Wert von einem seiner Member.</span><span class="sxs-lookup"><span data-stu-id="d950e-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d950e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d950e-113">Example</span></span>  
 <span data-ttu-id="d950e-114">Das folgende Beispiel zeigt verschiedene Möglichkeiten zum Abrufen der aktuellen Eigenschaften des ein <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="d950e-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="d950e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d950e-115">See Also</span></span>  
 [<span data-ttu-id="d950e-116">Benutzeroberflächenautomatisierungs-Eigenschaften für Clients</span><span class="sxs-lookup"><span data-stu-id="d950e-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="d950e-117">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d950e-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="d950e-118">Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients</span><span class="sxs-lookup"><span data-stu-id="d950e-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
