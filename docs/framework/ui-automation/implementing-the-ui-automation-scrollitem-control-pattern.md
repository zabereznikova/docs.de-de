---
title: Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Lesen Sie die Richtlinien und Konventionen zum Implementieren des ScrollItem-Steuerelement Musters in der Benutzeroberflächen Automatisierung. Siehe erforderliche Member für die IScrollItemProvider-Schnittstelle.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 3274f75af0ca055547a75fd8db6384ddb0f59483
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239236"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="788eb-104">Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="788eb-104">Implementing the UI Automation ScrollItem Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="788eb-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="788eb-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="788eb-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="788eb-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="788eb-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren des <xref:System.Windows.Automation.Provider.IScrollItemProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="788eb-107">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="788eb-108">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="788eb-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="788eb-109">Das <xref:System.Windows.Automation.ScrollItemPattern>-Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.IScrollProvider> implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="788eb-109">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="788eb-110">Dieses Steuerelementmuster dient als Kommunikationskanal zwischen einem untergeordneten Steuerelement und dessen Container, um sicherzustellen, dass der Container den aktuell sichtbaren Inhalt (oder die Region) innerhalb des Viewports ändern kann, um das untergeordnete Steuerelement anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="788eb-110">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="788eb-111">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="788eb-111">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="788eb-112">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="788eb-112">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="788eb-113">Beachten Sie beim Implementieren des ScrollItem-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="788eb-113">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="788eb-114">In einem Window- oder Canvas-Steuerelement enthaltene Elemente müssen die IScrollItemProvider-Schnittstelle nicht implementieren.</span><span class="sxs-lookup"><span data-stu-id="788eb-114">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="788eb-115">Stattdessen können sie jedoch einen gültigen Speicherort für die <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="788eb-115">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="788eb-116">Dadurch kann eine Benutzeroberflächenautomatisierungs-Clientanwendung die <xref:System.Windows.Automation.ScrollPattern>-Steuerelementmustermethoden im Container verwenden, um das untergeordnete Element anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="788eb-116">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>

## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="788eb-117">Erforderliche Member für IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="788eb-117">Required Members for IScrollItemProvider</span></span>  

 <span data-ttu-id="788eb-118">Die folgende Methode ist zum Implementieren der IScrollProvider-Schnittstelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="788eb-118">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="788eb-119">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="788eb-119">Required members</span></span>|<span data-ttu-id="788eb-120">Memberart</span><span class="sxs-lookup"><span data-stu-id="788eb-120">Member type</span></span>|<span data-ttu-id="788eb-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="788eb-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="788eb-122">-Methode</span><span class="sxs-lookup"><span data-stu-id="788eb-122">-   Method</span></span>|<span data-ttu-id="788eb-123">Keine</span><span class="sxs-lookup"><span data-stu-id="788eb-123">None</span></span>|  
  
 <span data-ttu-id="788eb-124">Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="788eb-124">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="788eb-125">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="788eb-125">Exceptions</span></span>  

 <span data-ttu-id="788eb-126">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="788eb-126">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="788eb-127">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="788eb-127">Exception Type</span></span>|<span data-ttu-id="788eb-128">Bedingung</span><span class="sxs-lookup"><span data-stu-id="788eb-128">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="788eb-129">Wenn ein Element nicht in die Ansicht gescrollt werden kann:</span><span class="sxs-lookup"><span data-stu-id="788eb-129">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="788eb-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="788eb-130">See also</span></span>

- [<span data-ttu-id="788eb-131">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="788eb-131">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="788eb-132">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="788eb-132">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="788eb-133">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="788eb-133">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="788eb-134">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="788eb-134">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="788eb-135">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="788eb-135">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
