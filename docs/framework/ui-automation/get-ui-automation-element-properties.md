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
ms.openlocfilehash: 93e0fba4288ba3231bfed45252bdaa78892d008c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330765"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="d1d90-102">Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d1d90-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="d1d90-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d1d90-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d1d90-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d1d90-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d1d90-105">In diesem Thema wird gezeigt, wie zum Abrufen der Eigenschaften einer [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Element.</span><span class="sxs-lookup"><span data-stu-id="d1d90-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="d1d90-106">Erhalten Sie einen aktuellen Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="d1d90-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="d1d90-107">Abrufen der <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft, die Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d1d90-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="d1d90-108">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Current%2A> Struktur der Eigenschaft an, und erhalten den Wert von eins ihrer Elemente.</span><span class="sxs-lookup"><span data-stu-id="d1d90-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="d1d90-109">Abrufen eines Werts für die zwischengespeicherten Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="d1d90-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="d1d90-110">Abrufen der <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft, die Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d1d90-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="d1d90-111">Die Eigenschaft muss angegeben wurden die <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="d1d90-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="d1d90-112">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Cached%2A> Struktur der Eigenschaft an, und erhalten den Wert von eins ihrer Elemente.</span><span class="sxs-lookup"><span data-stu-id="d1d90-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d90-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1d90-113">Example</span></span>  
 <span data-ttu-id="d1d90-114">Das folgende Beispiel zeigt verschiedene Möglichkeiten zum Abrufen der aktuellen Eigenschaften des ein <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="d1d90-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d90-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1d90-115">See also</span></span>

- [<span data-ttu-id="d1d90-116">Benutzeroberflächenautomatisierungs-Eigenschaften für Clients</span><span class="sxs-lookup"><span data-stu-id="d1d90-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="d1d90-117">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d1d90-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="d1d90-118">Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients</span><span class="sxs-lookup"><span data-stu-id="d1d90-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
