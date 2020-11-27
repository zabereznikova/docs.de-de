---
title: Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Lesen Sie die Richtlinien und Konventionen zum Implementieren des TableItem-Steuerelement Musters in der Benutzeroberflächen Automatisierung. Sie müssen erforderliche Member für die ITableItemProvider-Schnittstelle kennen.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 5e83f68772de3026fe8bcb265a11999e0b85a164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265673"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="d325a-104">Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d325a-104">Implementing the UI Automation TableItem Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="d325a-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d325a-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d325a-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d325a-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d325a-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITableItemProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d325a-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="d325a-108">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d325a-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="d325a-109">Das <xref:System.Windows.Automation.TableItemPattern>-Steuerelementmuster wird verwendet, um untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.ITableProvider> implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="d325a-109">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="d325a-110">Zugriff auf Funktionen einzelner Zellen wird durch die gleichzeitig erforderliche Implementierung von <xref:System.Windows.Automation.Provider.IGridItemProvider> bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d325a-110">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="d325a-111">Dieses Steuerelementmuster ist analog zu <xref:System.Windows.Automation.Provider.IGridItemProvider> mit dem Unterschied, dass jedes Steuerelement, das <xref:System.Windows.Automation.Provider.ITableItemProvider> implementiert, programmgesteuert die Beziehung zwischen der einzelnen Zelle und deren Zeilen- und Spalteninformationen verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="d325a-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="d325a-112">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d325a-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="d325a-113">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="d325a-113">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="d325a-114">Weitere Informationen zu verwandten Raster Elementen finden Sie unter [Implementieren des GridItem-Steuerelement Musters der Benutzeroberflächen Automatisierung](implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="d325a-114">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>

## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="d325a-115">Erforderliche Member für ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="d325a-115">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="d325a-116">Erforderlicher Member</span><span class="sxs-lookup"><span data-stu-id="d325a-116">Required member</span></span>|<span data-ttu-id="d325a-117">Memberart</span><span class="sxs-lookup"><span data-stu-id="d325a-117">Member type</span></span>|<span data-ttu-id="d325a-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d325a-118">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="d325a-119">Methode</span><span class="sxs-lookup"><span data-stu-id="d325a-119">Method</span></span>|<span data-ttu-id="d325a-120">Keine</span><span class="sxs-lookup"><span data-stu-id="d325a-120">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="d325a-121">Methode</span><span class="sxs-lookup"><span data-stu-id="d325a-121">Method</span></span>|<span data-ttu-id="d325a-122">Keine</span><span class="sxs-lookup"><span data-stu-id="d325a-122">None</span></span>|  
  
 <span data-ttu-id="d325a-123">Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d325a-123">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="d325a-124">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="d325a-124">Exceptions</span></span>  

 <span data-ttu-id="d325a-125">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d325a-125">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d325a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d325a-126">See also</span></span>

- [<span data-ttu-id="d325a-127">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d325a-127">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="d325a-128">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d325a-128">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="d325a-129">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="d325a-129">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="d325a-130">Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d325a-130">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="d325a-131">Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d325a-131">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="d325a-132">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="d325a-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="d325a-133">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d325a-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
