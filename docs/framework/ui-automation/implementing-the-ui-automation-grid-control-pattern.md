---
title: Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Informationen zu Richtlinien und Konventionen für das Implementieren des GridPattern Grid-Steuerelement Musters in der Benutzeroberflächen Automatisierung. Erfahren Sie, wie Sie die IGridProvider-Schnittstelle implementieren.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, grid
- grid control pattern
- UI Automation, grid control pattern
ms.assetid: 234d11a0-7ce7-4309-8989-2f4720e02f78
ms.openlocfilehash: 2290fd91c8eee0ab969eef2827d3c7440ef21e20
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274880"
---
# <a name="implementing-the-ui-automation-grid-control-pattern"></a><span data-ttu-id="910f1-104">Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="910f1-104">Implementing the UI Automation Grid Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="910f1-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="910f1-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="910f1-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="910f1-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="910f1-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IGridProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="910f1-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="910f1-108">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="910f1-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="910f1-109">Das <xref:System.Windows.Automation.GridPattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die als Container für eine Auflistung von untergeordneten Elementen dienen.</span><span class="sxs-lookup"><span data-stu-id="910f1-109">The <xref:System.Windows.Automation.GridPattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="910f1-110">Die untergeordneten Elemente dieses Elements müssen <xref:System.Windows.Automation.Provider.IGridItemProvider> implementieren und in einem zweidimensionalen logischen Koordinatensystem angeordnet sein, das zeilen- und spaltenweise durchlaufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="910f1-110">The children of this element must implement <xref:System.Windows.Automation.Provider.IGridItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="910f1-111">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="910f1-111">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="910f1-112">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="910f1-112">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="910f1-113">Beachten Sie beim Implementieren des Grid-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="910f1-113">When implementing the Grid control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="910f1-114">Grid-Koordinaten sind nullbasiert, wobei die obere linke Zelle (oder die obere rechte Zelle, je nach Gebietsschema) die Koordinaten (0,0) aufweist.</span><span class="sxs-lookup"><span data-stu-id="910f1-114">Grid coordinates are zero-based with the upper left (or upper right cell depending on locale) having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="910f1-115">Auch wenn eine Zelle leer ist, muss ein Benutzeroberflächenautomatisierungs-Element zurückgegeben werden, um die <xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A> -Eigenschaft dieser Zelle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="910f1-115">If a cell is empty, a UI Automation element must still be returned in order to support the <xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A> property for that cell.</span></span> <span data-ttu-id="910f1-116">Dies ist möglich, wenn das Layout von untergeordneten Elementen im Raster dem eines unregelmäßigen Arrays entspricht (siehe folgendes Beispiel).</span><span class="sxs-lookup"><span data-stu-id="910f1-116">This is possible when the layout of child elements in the grid is similar to a ragged array (see example below).</span></span>  
  
 <span data-ttu-id="910f1-117">![Windows-Explorer-Ansicht mit Flatterlayout.](./media/uia-gridpattern-ragged-array.PNG "UIA_GridPattern_Ragged_Array")</span><span class="sxs-lookup"><span data-stu-id="910f1-117">![Windows Explorer view showing ragged layout.](./media/uia-gridpattern-ragged-array.PNG "UIA_GridPattern_Ragged_Array")</span></span>  
<span data-ttu-id="910f1-118">Beispiel für ein Grid-Steuerelement mit leeren Koordinaten</span><span class="sxs-lookup"><span data-stu-id="910f1-118">Example of a Grid Control with Empty Coordinates</span></span>  
  
- <span data-ttu-id="910f1-119">Ein Raster mit einem einzelnen Element muss weiterhin <xref:System.Windows.Automation.Provider.IGridProvider> implementieren, wenn es logisch als Raster gilt.</span><span class="sxs-lookup"><span data-stu-id="910f1-119">A grid with a single item is still required to implement <xref:System.Windows.Automation.Provider.IGridProvider> if it is logically considered to be a grid.</span></span> <span data-ttu-id="910f1-120">Die Anzahl untergeordneter Elemente im Raster ist unwesentlich.</span><span class="sxs-lookup"><span data-stu-id="910f1-120">The number of child items in the grid is immaterial.</span></span>  
  
- <span data-ttu-id="910f1-121">Ausgeblendete Zeilen und Spalten können je nach der Anbieterimplementierung in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur geladen werden. Daher werden sie in den Eigenschaften <xref:System.Windows.Automation.GridPattern.GridPatternInformation.RowCount%2A> und <xref:System.Windows.Automation.GridPattern.GridPatternInformation.ColumnCount%2A> angegeben.</span><span class="sxs-lookup"><span data-stu-id="910f1-121">Hidden rows and columns, depending on the provider implementation, may be loaded in the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree and therefore will be reflected in the <xref:System.Windows.Automation.GridPattern.GridPatternInformation.RowCount%2A> and <xref:System.Windows.Automation.GridPattern.GridPatternInformation.ColumnCount%2A> properties.</span></span> <span data-ttu-id="910f1-122">Wenn die ausgeblendeten Zeilen und Spalten noch nicht geladen wurden, sollten sie nicht gezählt werden.</span><span class="sxs-lookup"><span data-stu-id="910f1-122">If the hidden rows and columns have not yet been loaded, they should not be counted.</span></span>  
  
- <span data-ttu-id="910f1-123"><xref:System.Windows.Automation.Provider.IGridProvider> ermöglicht keine aktive Bearbeitung eines Rasters. <xref:System.Windows.Automation.Provider.ITransformProvider> muss implementiert werden, um diese Funktionalität zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="910f1-123"><xref:System.Windows.Automation.Provider.IGridProvider> does not enable active manipulation of a grid; <xref:System.Windows.Automation.Provider.ITransformProvider> must be implemented to enable this functionality.</span></span>  
  
- <span data-ttu-id="910f1-124">Verwenden Sie einen <xref:System.Windows.Automation.StructureChangedEventHandler> , um Änderungen an der Struktur oder am Layout des Raster zu erfassen, z. B. Zellen, die hinzugefügt, entfernt oder zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="910f1-124">Use a <xref:System.Windows.Automation.StructureChangedEventHandler> to listen for structural or layout changes to the grid such as cells that have been added, removed, or merged.</span></span>  
  
- <span data-ttu-id="910f1-125">Verwenden Sie einen <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> , um den Durchlauf durch die Elemente oder Zellen eines Rasters zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="910f1-125">Use a <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> to track traversal through the items or cells of a grid.</span></span>  
  
<a name="Required_Members_for_IGridProvider"></a>

## <a name="required-members-for-igridprovider"></a><span data-ttu-id="910f1-126">Erforderliche Member für IGridProvider</span><span class="sxs-lookup"><span data-stu-id="910f1-126">Required Members for IGridProvider</span></span>  

 <span data-ttu-id="910f1-127">Zum Implementieren der IGridProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.</span><span class="sxs-lookup"><span data-stu-id="910f1-127">The following properties and methods are required for implementing the IGridProvider interface.</span></span>  
  
|<span data-ttu-id="910f1-128">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="910f1-128">Required members</span></span>|<span data-ttu-id="910f1-129">type</span><span class="sxs-lookup"><span data-stu-id="910f1-129">Type</span></span>|<span data-ttu-id="910f1-130">Notizen</span><span class="sxs-lookup"><span data-stu-id="910f1-130">Notes</span></span>|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A>|<span data-ttu-id="910f1-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="910f1-131">Property</span></span>|<span data-ttu-id="910f1-132">Keine</span><span class="sxs-lookup"><span data-stu-id="910f1-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>|<span data-ttu-id="910f1-133">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="910f1-133">Property</span></span>|<span data-ttu-id="910f1-134">Keine</span><span class="sxs-lookup"><span data-stu-id="910f1-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A>|<span data-ttu-id="910f1-135">Methode</span><span class="sxs-lookup"><span data-stu-id="910f1-135">Method</span></span>|<span data-ttu-id="910f1-136">Keine</span><span class="sxs-lookup"><span data-stu-id="910f1-136">None</span></span>|  
  
 <span data-ttu-id="910f1-137">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="910f1-137">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="910f1-138">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="910f1-138">Exceptions</span></span>  

 <span data-ttu-id="910f1-139">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="910f1-139">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="910f1-140">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="910f1-140">Exception type</span></span>|<span data-ttu-id="910f1-141">Bedingung</span><span class="sxs-lookup"><span data-stu-id="910f1-141">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> <span data-ttu-id="910f1-142">-, Wenn die angeforderte Zeilen Koordinate größer als ist <xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A> oder die Spalten Koordinate größer als ist <xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A> .</span><span class="sxs-lookup"><span data-stu-id="910f1-142">-   If the requested row coordinate is larger than the <xref:System.Windows.Automation.Provider.IGridProvider.RowCount%2A> or the column coordinate is larger than the <xref:System.Windows.Automation.Provider.IGridProvider.ColumnCount%2A>.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IGridProvider.GetItem%2A><br /><br /> <span data-ttu-id="910f1-143">-, Wenn eine der angeforderten Zeilen-oder Spalten Koordinaten kleiner als 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="910f1-143">-   If either of the requested row or column coordinates is less than zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="910f1-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="910f1-144">See also</span></span>

- [<span data-ttu-id="910f1-145">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="910f1-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="910f1-146">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="910f1-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="910f1-147">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="910f1-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="910f1-148">Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="910f1-148">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="910f1-149">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="910f1-149">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="910f1-150">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="910f1-150">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
