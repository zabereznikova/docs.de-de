---
title: Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0346b70b4400c5f7a8d282d945e029701973dad1
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884457"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="901b0-102">Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="901b0-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="901b0-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="901b0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="901b0-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="901b0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="901b0-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren der <xref:System.Windows.Automation.Provider.IScrollItemProvider>, einschließlich Informationen zu Eigenschaften, Methoden und Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="901b0-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="901b0-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="901b0-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="901b0-107">Die <xref:System.Windows.Automation.ScrollItemPattern> -Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, implementieren <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="901b0-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="901b0-108">Dieses Steuerelementmuster dient als Kommunikationskanal zwischen einem untergeordneten Steuerelement und dessen Container, um sicherzustellen, dass der Container den aktuell sichtbaren Inhalt (oder die Region) innerhalb des Viewports ändern kann, um das untergeordnete Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="901b0-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="901b0-109">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="901b0-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="901b0-110">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="901b0-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="901b0-111">Beachten Sie beim Implementieren des ScrollItem-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="901b0-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="901b0-112">In einem Window- oder Canvas-Steuerelement enthaltene Elemente müssen die IScrollItemProvider-Schnittstelle nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="901b0-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="901b0-113">Als Alternative können jedoch, sie müssen zur Verfügung stellen eines gültigen Speicherort für die <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="901b0-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="901b0-114">Dadurch kann eine Benutzeroberflächenautomatisierungs-Clientanwendung verwendet die <xref:System.Windows.Automation.ScrollPattern> -steuerelementmustermethoden im Container auf das untergeordnete Element anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="901b0-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="901b0-115">Erforderliche Member für IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="901b0-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="901b0-116">Die folgende Methode ist zum Implementieren der IScrollProvider-Schnittstelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="901b0-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="901b0-117">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="901b0-117">Required members</span></span>|<span data-ttu-id="901b0-118">Memberart</span><span class="sxs-lookup"><span data-stu-id="901b0-118">Member type</span></span>|<span data-ttu-id="901b0-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="901b0-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="901b0-120">-Methode</span><span class="sxs-lookup"><span data-stu-id="901b0-120">-   Method</span></span>|<span data-ttu-id="901b0-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="901b0-121">None</span></span>|  
  
 <span data-ttu-id="901b0-122">Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="901b0-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="901b0-123">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="901b0-123">Exceptions</span></span>  
 <span data-ttu-id="901b0-124">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="901b0-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="901b0-125">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="901b0-125">Exception Type</span></span>|<span data-ttu-id="901b0-126">Bedingung</span><span class="sxs-lookup"><span data-stu-id="901b0-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="901b0-127">Wenn ein Element nicht in die Ansicht gescrollt werden kann:</span><span class="sxs-lookup"><span data-stu-id="901b0-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="901b0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="901b0-128">See Also</span></span>  
 [<span data-ttu-id="901b0-129">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="901b0-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="901b0-130">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="901b0-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="901b0-131">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="901b0-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="901b0-132">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="901b0-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="901b0-133">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="901b0-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
