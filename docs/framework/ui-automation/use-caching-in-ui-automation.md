---
title: "Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung"
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
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 9576389c7245810eeef3c86926e479dedfdfbb69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="7cb19-102">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="7cb19-102">Use Caching in UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="7cb19-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7cb19-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7cb19-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="7cb19-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7cb19-105">In diesem Abschnitt wird gezeigt, wie ein Zwischenspeichern von <xref:System.Windows.Automation.AutomationElement> -Eigenschaften und Steuerelementmustern implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="7cb19-105">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="7cb19-106">Aktivieren einer Cacheanforderung</span><span class="sxs-lookup"><span data-stu-id="7cb19-106">Activate a Cache Request</span></span>  
  
1.  <span data-ttu-id="7cb19-107">Erstellen Sie eine <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="7cb19-107">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="7cb19-108">Geben Sie über <xref:System.Windows.Automation.CacheRequest.Add%2A>die Eigenschaften und Muster an, die zwischengespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7cb19-108">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3.  <span data-ttu-id="7cb19-109">Geben Sie den Umfang des Zwischenspeicherns an, indem Sie die <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> -Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="7cb19-109">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4.  <span data-ttu-id="7cb19-110">Geben Sie die Ansicht der Unterstruktur an, indem Sie die <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> -Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="7cb19-110">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5.  <span data-ttu-id="7cb19-111">Legen Sie die <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> -Eigenschaft auf <xref:System.Windows.Automation.AutomationElementMode.None> fest, wenn Sie die Effizienz dadurch steigern möchten, dass auf das Abrufen eines vollständigen Verweises auf Objekte verzichtet wird.</span><span class="sxs-lookup"><span data-stu-id="7cb19-111">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="7cb19-112">(Dadurch wird es unmöglich, aktuelle Werte aus diesen Objekten abzurufen.)</span><span class="sxs-lookup"><span data-stu-id="7cb19-112">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6.  <span data-ttu-id="7cb19-113">Aktivieren Sie die Anforderung, indem Sie <xref:System.Windows.Automation.CacheRequest.Activate%2A> in einem `using` -Block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cb19-113">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>  
  
 <span data-ttu-id="7cb19-114">Deaktivieren Sie nach dem Abrufen von <xref:System.Windows.Automation.AutomationElement> -Objekten oder dem Abonnieren von Ereignissen die Anforderung, indem Sie <xref:System.Windows.Automation.CacheRequest.Pop%2A> verwenden (wenn <xref:System.Windows.Automation.CacheRequest.Push%2A> verwendet wurde) oder indem Sie das durch <xref:System.Windows.Automation.CacheRequest.Activate%2A>erstellte Objekt löschen.</span><span class="sxs-lookup"><span data-stu-id="7cb19-114">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="7cb19-115">Verwenden Sie <xref:System.Windows.Automation.CacheRequest.Activate%2A> in einem `using` -Block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="7cb19-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="7cb19-116">Zwischenspeichern von AutomationElement-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7cb19-116">Cache AutomationElement Properties</span></span>  
  
1.  <span data-ttu-id="7cb19-117">Während ein <xref:System.Windows.Automation.CacheRequest> aktiv ist, können Sie <xref:System.Windows.Automation.AutomationElement> -Objekte über <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> oder <xref:System.Windows.Automation.AutomationElement.FindAll%2A>abrufen. Sie können ein <xref:System.Windows.Automation.AutomationElement> -Objekt aber auch als Quelle eines Ereignisses abrufen, für das Sie eine Registrierung vorgenommen haben, als das <xref:System.Windows.Automation.CacheRequest> -Objekt aktiv war.</span><span class="sxs-lookup"><span data-stu-id="7cb19-117">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="7cb19-118">(Sie können einen Cache auch erstellen, indem Sie ein <xref:System.Windows.Automation.CacheRequest> an GetUpdatedCache oder an eine der <xref:System.Windows.Automation.TreeWalker> -Methoden übergeben.)</span><span class="sxs-lookup"><span data-stu-id="7cb19-118">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="7cb19-119">Verwenden Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> , oder rufen Sie eine Eigenschaft aus der <xref:System.Windows.Automation.AutomationElement.Cached%2A> -Eigenschaft des <xref:System.Windows.Automation.AutomationElement>-Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="7cb19-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="7cb19-120">Abrufen von zwischengespeicherten Mustern und deren Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7cb19-120">Obtain Cached Patterns and Their Properties</span></span>  
  
1.  <span data-ttu-id="7cb19-121">Während ein <xref:System.Windows.Automation.CacheRequest> aktiv ist, können Sie <xref:System.Windows.Automation.AutomationElement> -Objekte über <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> oder <xref:System.Windows.Automation.AutomationElement.FindAll%2A>abrufen. Sie können ein <xref:System.Windows.Automation.AutomationElement> -Objekt aber auch als Quelle eines Ereignisses abrufen, für das Sie eine Registrierung vorgenommen haben, als das <xref:System.Windows.Automation.CacheRequest> -Objekt aktiv war.</span><span class="sxs-lookup"><span data-stu-id="7cb19-121">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="7cb19-122">(Sie können einen Cache auch erstellen, indem Sie ein <xref:System.Windows.Automation.CacheRequest> an GetUpdatedCache oder an eine der <xref:System.Windows.Automation.TreeWalker> -Methoden übergeben.)</span><span class="sxs-lookup"><span data-stu-id="7cb19-122">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="7cb19-123">Verwenden Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> , um ein zwischengespeichertes Muster abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7cb19-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3.  <span data-ttu-id="7cb19-124">Rufen Sie Eigenschaftswerte aus der `Cached` -Eigenschaft des Steuerelementmusters ab.</span><span class="sxs-lookup"><span data-stu-id="7cb19-124">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cb19-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7cb19-125">Example</span></span>  
 <span data-ttu-id="7cb19-126">Im folgenden Codebeispiel werden die verschiedenen Möglichkeiten des Zwischenspeicherns gezeigt. Dabei wird <xref:System.Windows.Automation.CacheRequest.Activate%2A> verwendet wird, um das <xref:System.Windows.Automation.CacheRequest>-Objekt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cb19-126">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="7cb19-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7cb19-127">Example</span></span>  
 <span data-ttu-id="7cb19-128">Im folgenden Codebeispiel werden die verschiedenen Möglichkeiten des Zwischenspeicherns gezeigt. Dabei wird <xref:System.Windows.Automation.CacheRequest.Push%2A> verwendet wird, um das <xref:System.Windows.Automation.CacheRequest>-Objekt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7cb19-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="7cb19-129">Sie sollten möglichst <xref:System.Windows.Automation.CacheRequest.Activate%2A>verwenden, es sei denn, Sie möchten Cacheanforderungen schachteln.</span><span class="sxs-lookup"><span data-stu-id="7cb19-129">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="7cb19-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cb19-130">See Also</span></span>  
 [<span data-ttu-id="7cb19-131">Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients</span><span class="sxs-lookup"><span data-stu-id="7cb19-131">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
