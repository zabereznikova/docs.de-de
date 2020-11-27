---
title: Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
description: In den Anweisungen und einem Beispiel wird gezeigt, wie Sie die aktuellen oder zwischengespeicherten Eigenschaften eines Benutzeroberflächenautomatisierungs-Elements abrufen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 34a42355acce0beafbb9658baf6032e4e7e19fcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276424"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="c5459-103">Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="c5459-103">Get UI Automation Element Properties</span></span>

> [!NOTE]
> <span data-ttu-id="c5459-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c5459-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c5459-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="c5459-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="c5459-106">In diesem Thema wird gezeigt, wie Eigenschaften eines-Elements abgerufen werden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5459-106">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="c5459-107">Aktuellen Eigenschafts Wert erhalten</span><span class="sxs-lookup"><span data-stu-id="c5459-107">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="c5459-108">Rufen Sie das ab <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5459-108">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="c5459-109">Rufen <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> Sie auf, oder rufen <xref:System.Windows.Automation.AutomationElement.Current%2A> Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.</span><span class="sxs-lookup"><span data-stu-id="c5459-109">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="c5459-110">Erhalten eines zwischengespeicherten Eigenschafts Werts</span><span class="sxs-lookup"><span data-stu-id="c5459-110">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="c5459-111">Rufen Sie das ab <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5459-111">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="c5459-112">Die-Eigenschaft muss in angegeben werden <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="c5459-112">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="c5459-113">Rufen <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> Sie auf, oder rufen <xref:System.Windows.Automation.AutomationElement.Cached%2A> Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.</span><span class="sxs-lookup"><span data-stu-id="c5459-113">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5459-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5459-114">Example</span></span>  

 <span data-ttu-id="c5459-115">Das folgende Beispiel zeigt verschiedene Möglichkeiten, die aktuellen Eigenschaften eines abzurufen <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="c5459-115">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="c5459-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5459-116">See also</span></span>

- [<span data-ttu-id="c5459-117">Benutzeroberflächenautomatisierungs-Eigenschaften für Clients</span><span class="sxs-lookup"><span data-stu-id="c5459-117">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="c5459-118">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="c5459-118">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="c5459-119">Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients</span><span class="sxs-lookup"><span data-stu-id="c5459-119">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
