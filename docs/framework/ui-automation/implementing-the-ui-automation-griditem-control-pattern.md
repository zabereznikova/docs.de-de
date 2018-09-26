---
title: Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 68de80e4a01de27c16c0ed85c4177c562d5e328b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47204715"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="94400-102">Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94400-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="94400-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="94400-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="94400-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="94400-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="94400-105">Dieses Thema enthält Richtlinien und Konventionen zum Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider>, einschließlich Informationen über Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="94400-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="94400-106">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="94400-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="94400-107">Die <xref:System.Windows.Automation.GridItemPattern> -Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, implementieren <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="94400-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="94400-108">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="94400-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="94400-109">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="94400-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="94400-110">Bei der Implementierung <xref:System.Windows.Automation.Provider.IGridProvider>, beachten Sie die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="94400-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="94400-111">Rasterkoordinaten (Grid-Koordinaten) sind nullbasiert, wobei die obere linke Zelle die Koordinaten (0, 0) hat.</span><span class="sxs-lookup"><span data-stu-id="94400-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="94400-112">Zusammengeführte Zellen ihren <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> und <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> Eigenschaften basierend auf der zugrunde liegenden Ankerzelle vom Benutzeroberflächenautomatisierungs-Anbieter definiert.</span><span class="sxs-lookup"><span data-stu-id="94400-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="94400-113">In der Regel sind dies die oberste Zeile und die am weitesten links liegende Spalte.</span><span class="sxs-lookup"><span data-stu-id="94400-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="94400-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> bietet keine aktive Bearbeitung des Rasters wie etwa zusammenführen oder Teilen von Zellen.</span><span class="sxs-lookup"><span data-stu-id="94400-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="94400-115">Steuert, implementieren <xref:System.Windows.Automation.Provider.IGridItemProvider> in der Regel durchlaufen werden kann (d. h. ein Benutzeroberflächenautomatisierungs-Client kann zu benachbarten Steuerelementen wechseln) mithilfe der Tastatur.</span><span class="sxs-lookup"><span data-stu-id="94400-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="94400-116">Erforderliche Member für IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="94400-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="94400-117">Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider> erforderlich.</span><span class="sxs-lookup"><span data-stu-id="94400-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="94400-118">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="94400-118">Required members</span></span>|<span data-ttu-id="94400-119">Memberart</span><span class="sxs-lookup"><span data-stu-id="94400-119">Member type</span></span>|<span data-ttu-id="94400-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94400-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="94400-121">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94400-121">Property</span></span>|<span data-ttu-id="94400-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="94400-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="94400-123">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94400-123">Property</span></span>|<span data-ttu-id="94400-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="94400-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="94400-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94400-125">Property</span></span>|<span data-ttu-id="94400-126">Keiner</span><span class="sxs-lookup"><span data-stu-id="94400-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="94400-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94400-127">Property</span></span>|<span data-ttu-id="94400-128">Keiner</span><span class="sxs-lookup"><span data-stu-id="94400-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="94400-129">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="94400-129">Property</span></span>|<span data-ttu-id="94400-130">Keiner</span><span class="sxs-lookup"><span data-stu-id="94400-130">None</span></span>|  
  
 <span data-ttu-id="94400-131">Diesem Steuerelementmuster sind keine Methoden oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="94400-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="94400-132">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="94400-132">Exceptions</span></span>  
 <span data-ttu-id="94400-133">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="94400-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94400-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94400-134">See Also</span></span>  
 [<span data-ttu-id="94400-135">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94400-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="94400-136">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="94400-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="94400-137">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="94400-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="94400-138">Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94400-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="94400-139">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="94400-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="94400-140">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94400-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
