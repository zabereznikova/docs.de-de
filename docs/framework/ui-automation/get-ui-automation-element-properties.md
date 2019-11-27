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
ms.openlocfilehash: 1b82302ff89d2e8407871cbfba6c10e8322ac4e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435502"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="04384-102">Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="04384-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="04384-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="04384-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="04384-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="04384-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="04384-105">In diesem Thema wird gezeigt, wie Eigenschaften eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Elements abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="04384-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="04384-106">Aktuellen Eigenschafts Wert erhalten</span><span class="sxs-lookup"><span data-stu-id="04384-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="04384-107">Rufen Sie den <xref:System.Windows.Automation.AutomationElement> ab, dessen Eigenschaft abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="04384-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="04384-108">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>auf, oder rufen Sie die <xref:System.Windows.Automation.AutomationElement.Current%2A> Eigenschafts Struktur ab, und rufen Sie den Wert von einem der Member ab.</span><span class="sxs-lookup"><span data-stu-id="04384-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="04384-109">Erhalten eines zwischengespeicherten Eigenschafts Werts</span><span class="sxs-lookup"><span data-stu-id="04384-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="04384-110">Rufen Sie den <xref:System.Windows.Automation.AutomationElement> ab, dessen Eigenschaft abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="04384-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="04384-111">Die-Eigenschaft muss in der <xref:System.Windows.Automation.CacheRequest>angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="04384-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="04384-112">Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>auf, oder rufen Sie die <xref:System.Windows.Automation.AutomationElement.Cached%2A> Eigenschafts Struktur ab, und rufen Sie den Wert von einem der Member ab.</span><span class="sxs-lookup"><span data-stu-id="04384-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04384-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04384-113">Example</span></span>  
 <span data-ttu-id="04384-114">Das folgende Beispiel zeigt verschiedene Möglichkeiten, die aktuellen Eigenschaften eines <xref:System.Windows.Automation.AutomationElement>abzurufen.</span><span class="sxs-lookup"><span data-stu-id="04384-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="04384-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04384-115">See also</span></span>

- [<span data-ttu-id="04384-116">UI Automation Properties for Clients</span><span class="sxs-lookup"><span data-stu-id="04384-116">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="04384-117">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="04384-117">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="04384-118">Caching in UI Automation Clients</span><span class="sxs-lookup"><span data-stu-id="04384-118">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
