---
title: Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: 832a53e072afc5533f2eeb7feb0cc326771cf23d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435255"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="dd554-102">Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="dd554-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="dd554-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dd554-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dd554-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="dd554-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="dd554-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider>, einschließlich Informationen über Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dd554-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="dd554-106">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="dd554-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="dd554-107">Das <xref:System.Windows.Automation.GridItemPattern>-Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.IGridProvider> implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="dd554-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="dd554-108">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="dd554-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="dd554-109">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="dd554-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="dd554-110">Beachten Sie bei der Implementierung von <xref:System.Windows.Automation.Provider.IGridProvider> die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="dd554-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="dd554-111">Rasterkoordinaten (Grid-Koordinaten) sind nullbasiert, wobei die obere linke Zelle die Koordinaten (0, 0) hat.</span><span class="sxs-lookup"><span data-stu-id="dd554-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="dd554-112">Zusammengeführte Zellen geben ihre <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>-Eigenschaft und <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>-Eigenschaft entsprechend ihrer zugrunde liegenden Ankerzelle an, wie sie vom Benutzeroberflächenautomatisierungs-Anbieter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="dd554-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="dd554-113">In der Regel sind dies die oberste Zeile und die am weitesten links liegende Spalte.</span><span class="sxs-lookup"><span data-stu-id="dd554-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="dd554-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> bietet keine aktive Bearbeitung des Rasters wie etwa Zusammenführen oder Teilen von Zellen.</span><span class="sxs-lookup"><span data-stu-id="dd554-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="dd554-115">Steuerelemente, die <xref:System.Windows.Automation.Provider.IGridItemProvider> implementieren, können meist mithilfe der Tastatur durchlaufen werden (d. h., ein Benutzeroberflächenautomatisierungs-Client kann zu benachbarten Steuerelementen wechseln).</span><span class="sxs-lookup"><span data-stu-id="dd554-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="dd554-116">Erforderliche Member für IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="dd554-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="dd554-117">Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IGridItemProvider>erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dd554-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="dd554-118">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="dd554-118">Required members</span></span>|<span data-ttu-id="dd554-119">Memberart</span><span class="sxs-lookup"><span data-stu-id="dd554-119">Member type</span></span>|<span data-ttu-id="dd554-120">Notizen</span><span class="sxs-lookup"><span data-stu-id="dd554-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="dd554-121">property</span><span class="sxs-lookup"><span data-stu-id="dd554-121">Property</span></span>|<span data-ttu-id="dd554-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="dd554-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="dd554-123">property</span><span class="sxs-lookup"><span data-stu-id="dd554-123">Property</span></span>|<span data-ttu-id="dd554-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="dd554-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="dd554-125">property</span><span class="sxs-lookup"><span data-stu-id="dd554-125">Property</span></span>|<span data-ttu-id="dd554-126">Keiner</span><span class="sxs-lookup"><span data-stu-id="dd554-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="dd554-127">property</span><span class="sxs-lookup"><span data-stu-id="dd554-127">Property</span></span>|<span data-ttu-id="dd554-128">Keiner</span><span class="sxs-lookup"><span data-stu-id="dd554-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="dd554-129">property</span><span class="sxs-lookup"><span data-stu-id="dd554-129">Property</span></span>|<span data-ttu-id="dd554-130">Keiner</span><span class="sxs-lookup"><span data-stu-id="dd554-130">None</span></span>|  
  
 <span data-ttu-id="dd554-131">Diesem Steuerelementmuster sind keine Methoden oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="dd554-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="dd554-132">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="dd554-132">Exceptions</span></span>  
 <span data-ttu-id="dd554-133">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="dd554-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd554-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd554-134">See also</span></span>

- [<span data-ttu-id="dd554-135">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="dd554-135">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="dd554-136">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="dd554-136">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="dd554-137">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="dd554-137">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="dd554-138">Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="dd554-138">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="dd554-139">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="dd554-139">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="dd554-140">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="dd554-140">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
