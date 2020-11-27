---
title: Implementieren des Dock-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Erfahren Sie, wie Sie das Steuerelement Muster für die Benutzeroberflächen Automatisierung implementieren Verwenden Sie das DockPattern-Steuerelement Muster, um die Andock Eigenschaften eines Steuer Elements anzuzeigen. Implementieren Sie IDockProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: 769808b190ade33ae52c53e03e1b4f77d4439df1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269625"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a><span data-ttu-id="2c6d7-105">Implementieren des Dock-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="2c6d7-105">Implementing the UI Automation Dock Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="2c6d7-106">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-106">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2c6d7-107">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="2c6d7-107">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2c6d7-108">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IDockProvider>, einschließlich Informationen über Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-108">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IDockProvider>, including information about properties.</span></span> <span data-ttu-id="2c6d7-109">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-109">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="2c6d7-110">Das <xref:System.Windows.Automation.DockPattern> -Steuerelementmuster wird verwendet, um Andockeigenschaften eines Steuerelements in einem Dockingcontainer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-110">The <xref:System.Windows.Automation.DockPattern> control pattern is used to expose the dock properties of a control within a docking container.</span></span> <span data-ttu-id="2c6d7-111">Ein Dockingcontainer ist ein Steuerelement, mit dem untergeordnete Elemente horizontal oder vertikal zueinander ausgerichtet werden können.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-111">A docking container is a control that allows you to arrange child elements horizontally and vertically, relative to each other.</span></span> <span data-ttu-id="2c6d7-112">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2c6d7-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
 <span data-ttu-id="2c6d7-113">![Andock-Container mit zwei angedockten untergeordneten Elementen.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span><span class="sxs-lookup"><span data-stu-id="2c6d7-113">![Docking container with two docked children.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")</span></span>  
<span data-ttu-id="2c6d7-114">Andockbeispiel aus Visual Studio, in dem das Fenster „Klassenansicht“ die DockPosition.Right und das Fenster „Fehlerliste“ die DockPosition.Bottom hat</span><span class="sxs-lookup"><span data-stu-id="2c6d7-114">Docking Example from Visual Studio Where "Class View" Window Is DockPosition.Right and "Error List" Window Is DockPosition.Bottom</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="2c6d7-115">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="2c6d7-115">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="2c6d7-116">Beachten Sie beim Implementieren des Dock-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="2c6d7-116">When implementing the Dock control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="2c6d7-117"><xref:System.Windows.Automation.Provider.IDockProvider> macht keine Eigenschaften des Dockingcontainers bzw. der Steuerelemente verfügbar, die neben dem aktuellen Steuerelement im Dockingcontainer angedockt sind.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-117"><xref:System.Windows.Automation.Provider.IDockProvider> does not expose any properties of the docking container or any properties of controls that are docked adjacent to the current control within the docking container.</span></span>  
  
- <span data-ttu-id="2c6d7-118">Steuerelemente werden relativ zueinander entsprechend ihrer aktuellen z-Reihenfolge angeordnet. Je höher ihre z-Reihenfolgenposition ist, desto weiter entfernt vom angegebenen Rand des Dockingcontainers werden sie platziert.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-118">Controls are docked relative to each other based on their current z-order; the higher their z-order placement, the farther they are placed from the specified edge of the docking container.</span></span>  
  
- <span data-ttu-id="2c6d7-119">Wenn die Größe des Dockingcontainers geändert wird, werden alle angedockten Steuerelemente im Container bündig zu derselben Kante neu positioniert, an der sie ursprünglich angedockt waren.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-119">If the docking container is resized, any docked controls within the container will be repositioned flush to the same edge to which they were originally docked.</span></span> <span data-ttu-id="2c6d7-120">Die Größe der angedockten Steuerelemente wird ebenfalls geändert, um den Platz innerhalb des Containers entsprechend dem Andockverhalten ihrer <xref:System.Windows.Automation.DockPosition>auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-120">The docked controls will also resize to fill any space within the container according to the docking behavior of their <xref:System.Windows.Automation.DockPosition>.</span></span> <span data-ttu-id="2c6d7-121">Wenn beispielsweise <xref:System.Windows.Automation.DockPosition.Top> angegeben ist, werden die linke und die rechte Seite des Steuerelements erweitert, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-121">For example, if <xref:System.Windows.Automation.DockPosition.Top> is specified, the left and right sides of the control will expand to fill any available space.</span></span> <span data-ttu-id="2c6d7-122">Wenn <xref:System.Windows.Automation.DockPosition.Fill> angegeben ist, werden alle vier Seiten des Steuerelements erweitert, um den verfügbaren Platz auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-122">If <xref:System.Windows.Automation.DockPosition.Fill> is specified, all four sides of the control will expand to fill any available space.</span></span>  
  
- <span data-ttu-id="2c6d7-123">Auf einem System mit mehreren Bildschirmen sollten Steuerelemente auf der linken oder rechten Seite des aktuellen Bildschirms andocken.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-123">On a multi-monitor system, controls should dock to the left or right side of the current monitor.</span></span> <span data-ttu-id="2c6d7-124">Ist dies nicht möglich, sollten sie auf der linken Seite des am weitesten links stehenden Bildschirms bzw. auf der rechten Seite des am weitesten rechts stehenden Bildschirms angedockt werden.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-124">If that is not possible, they should dock to the left side of the leftmost monitor or the right side of the rightmost monitor.</span></span>  
  
<a name="Required_Members_for_IDockProvider"></a>

## <a name="required-members-for-idockprovider"></a><span data-ttu-id="2c6d7-125">Erforderliche Member für IDockProvider</span><span class="sxs-lookup"><span data-stu-id="2c6d7-125">Required Members for IDockProvider</span></span>  

 <span data-ttu-id="2c6d7-126">Zum Implementieren der IDockProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-126">The following properties and methods are required for implementing the IDockProvider interface.</span></span>  
  
|<span data-ttu-id="2c6d7-127">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="2c6d7-127">Required members</span></span>|<span data-ttu-id="2c6d7-128">Memberart</span><span class="sxs-lookup"><span data-stu-id="2c6d7-128">Member type</span></span>|<span data-ttu-id="2c6d7-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c6d7-129">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|<span data-ttu-id="2c6d7-130">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2c6d7-130">Property</span></span>|<span data-ttu-id="2c6d7-131">Keine</span><span class="sxs-lookup"><span data-stu-id="2c6d7-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|<span data-ttu-id="2c6d7-132">Methode</span><span class="sxs-lookup"><span data-stu-id="2c6d7-132">Method</span></span>|<span data-ttu-id="2c6d7-133">Keine</span><span class="sxs-lookup"><span data-stu-id="2c6d7-133">None</span></span>|  
  
 <span data-ttu-id="2c6d7-134">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="2c6d7-135">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="2c6d7-135">Exceptions</span></span>  

 <span data-ttu-id="2c6d7-136">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-136">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="2c6d7-137">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="2c6d7-137">Exception type</span></span>|<span data-ttu-id="2c6d7-138">Bedingung</span><span class="sxs-lookup"><span data-stu-id="2c6d7-138">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> <span data-ttu-id="2c6d7-139">: Wenn ein Steuerelement nicht in der Lage ist, den angeforderten Andock Stil auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2c6d7-139">-   When a control is not able to execute the requested dock style.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c6d7-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c6d7-140">See also</span></span>

- [<span data-ttu-id="2c6d7-141">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="2c6d7-141">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="2c6d7-142">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="2c6d7-142">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="2c6d7-143">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="2c6d7-143">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="2c6d7-144">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="2c6d7-144">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="2c6d7-145">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="2c6d7-145">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
