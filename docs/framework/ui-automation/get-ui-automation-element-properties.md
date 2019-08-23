---
title: Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968964"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="826dc-102">Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="826dc-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="826dc-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="826dc-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="826dc-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="826dc-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="826dc-105">In diesem Thema wird gezeigt, wie Eigenschaften eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elements abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="826dc-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="826dc-106">Aktuellen Eigenschafts Wert erhalten</span><span class="sxs-lookup"><span data-stu-id="826dc-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="826dc-107">Rufen Sie <xref:System.Windows.Automation.AutomationElement> das ab, dessen Eigenschaft abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="826dc-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="826dc-108">Rufen <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>Sie auf, oder <xref:System.Windows.Automation.AutomationElement.Current%2A> rufen Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.</span><span class="sxs-lookup"><span data-stu-id="826dc-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="826dc-109">Erhalten eines zwischengespeicherten Eigenschafts Werts</span><span class="sxs-lookup"><span data-stu-id="826dc-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="826dc-110">Rufen Sie <xref:System.Windows.Automation.AutomationElement> das ab, dessen Eigenschaft abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="826dc-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="826dc-111">Die-Eigenschaft muss in <xref:System.Windows.Automation.CacheRequest>angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="826dc-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="826dc-112">Rufen <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>Sie auf, oder <xref:System.Windows.Automation.AutomationElement.Cached%2A> rufen Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.</span><span class="sxs-lookup"><span data-stu-id="826dc-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="826dc-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="826dc-113">Example</span></span>  
 <span data-ttu-id="826dc-114">Das folgende Beispiel zeigt verschiedene Möglichkeiten, die aktuellen Eigenschaften eines <xref:System.Windows.Automation.AutomationElement>abzurufen.</span><span class="sxs-lookup"><span data-stu-id="826dc-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="826dc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="826dc-115">See also</span></span>

- [<span data-ttu-id="826dc-116">Benutzeroberflächenautomatisierungs-Eigenschaften für Clients</span><span class="sxs-lookup"><span data-stu-id="826dc-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="826dc-117">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="826dc-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="826dc-118">Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients</span><span class="sxs-lookup"><span data-stu-id="826dc-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
