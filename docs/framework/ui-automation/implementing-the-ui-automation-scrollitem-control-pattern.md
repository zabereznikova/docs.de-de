---
title: Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 1e33a64e66bc084e8cc5f75ece2ac2a4d7ea85aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447142"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="ad7ca-102">Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ad7ca-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ad7ca-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ad7ca-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ad7ca-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ad7ca-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren des <xref:System.Windows.Automation.Provider.IScrollItemProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="ad7ca-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="ad7ca-107">Das <xref:System.Windows.Automation.ScrollItemPattern>-Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.IScrollProvider> implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="ad7ca-108">Dieses Steuerelementmuster dient als Kommunikationskanal zwischen einem untergeordneten Steuerelement und dessen Container, um sicherzustellen, dass der Container den aktuell sichtbaren Inhalt (oder die Region) innerhalb des Viewports ändern kann, um das untergeordnete Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="ad7ca-109">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ad7ca-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ad7ca-110">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="ad7ca-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="ad7ca-111">Beachten Sie beim Implementieren des ScrollItem-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="ad7ca-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ad7ca-112">In einem Window- oder Canvas-Steuerelement enthaltene Elemente müssen die IScrollItemProvider-Schnittstelle nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="ad7ca-113">Stattdessen können sie jedoch einen gültigen Speicherort für die <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="ad7ca-114">Dadurch kann eine Benutzeroberflächenautomatisierungs-Clientanwendung die <xref:System.Windows.Automation.ScrollPattern>-Steuerelementmustermethoden im Container verwenden, um das untergeordnete Element anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="ad7ca-115">Erforderliche Member für IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="ad7ca-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="ad7ca-116">Die folgende Methode ist zum Implementieren der IScrollProvider-Schnittstelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="ad7ca-117">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="ad7ca-117">Required members</span></span>|<span data-ttu-id="ad7ca-118">Memberart</span><span class="sxs-lookup"><span data-stu-id="ad7ca-118">Member type</span></span>|<span data-ttu-id="ad7ca-119">Notizen</span><span class="sxs-lookup"><span data-stu-id="ad7ca-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="ad7ca-120">-   Method</span><span class="sxs-lookup"><span data-stu-id="ad7ca-120">-   Method</span></span>|<span data-ttu-id="ad7ca-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="ad7ca-121">None</span></span>|  
  
 <span data-ttu-id="ad7ca-122">Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="ad7ca-123">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ad7ca-123">Exceptions</span></span>  
 <span data-ttu-id="ad7ca-124">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="ad7ca-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="ad7ca-125">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="ad7ca-125">Exception Type</span></span>|<span data-ttu-id="ad7ca-126">Bedingung</span><span class="sxs-lookup"><span data-stu-id="ad7ca-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="ad7ca-127">Wenn ein Element nicht in die Ansicht gescrollt werden kann:</span><span class="sxs-lookup"><span data-stu-id="ad7ca-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="ad7ca-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad7ca-128">See also</span></span>

- [<span data-ttu-id="ad7ca-129">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ad7ca-129">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ad7ca-130">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ad7ca-130">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ad7ca-131">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="ad7ca-131">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ad7ca-132">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="ad7ca-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ad7ca-133">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ad7ca-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
