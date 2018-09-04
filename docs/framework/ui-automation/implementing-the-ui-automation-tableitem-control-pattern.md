---
title: Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: db94a1a4588c2f889da8adb1cb3e47e208ce1211
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528671"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="a4a36-102">Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="a4a36-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="a4a36-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a4a36-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a4a36-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="a4a36-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a4a36-105">Dieses Thema enthält Richtlinien und Konventionen zum Implementieren von <xref:System.Windows.Automation.Provider.ITableItemProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a4a36-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="a4a36-106">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a4a36-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="a4a36-107">Die <xref:System.Windows.Automation.TableItemPattern> -Steuerelementmuster wird verwendet, um untergeordnete Steuerelemente von Containern zu unterstützen, implementieren <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="a4a36-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="a4a36-108">Der Zugriff auf Funktionen einzelner Zellen wird bereitgestellt, durch die erforderlichen gleichzeitigen Implementierung von <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="a4a36-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="a4a36-109">Dieses Steuerelementmuster ist analog zu <xref:System.Windows.Automation.Provider.IGridItemProvider> mit dem Unterschied, dass jedes implementieren Steuerelement <xref:System.Windows.Automation.Provider.ITableItemProvider> müssen, die Beziehung zwischen den einzelnen Zelle und die Zeilen- und programmgesteuert verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="a4a36-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="a4a36-110">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="a4a36-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="a4a36-111">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="a4a36-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="a4a36-112">Funktionen des zugehörigen Rasters-Element, finden Sie unter [implementieren das GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="a4a36-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="a4a36-113">Erforderliche Member für ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="a4a36-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="a4a36-114">Erforderlicher Member</span><span class="sxs-lookup"><span data-stu-id="a4a36-114">Required member</span></span>|<span data-ttu-id="a4a36-115">Memberart</span><span class="sxs-lookup"><span data-stu-id="a4a36-115">Member type</span></span>|<span data-ttu-id="a4a36-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4a36-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="a4a36-117">Methode</span><span class="sxs-lookup"><span data-stu-id="a4a36-117">Method</span></span>|<span data-ttu-id="a4a36-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="a4a36-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="a4a36-119">Methode</span><span class="sxs-lookup"><span data-stu-id="a4a36-119">Method</span></span>|<span data-ttu-id="a4a36-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="a4a36-120">None</span></span>|  
  
 <span data-ttu-id="a4a36-121">Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a4a36-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="a4a36-122">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="a4a36-122">Exceptions</span></span>  
 <span data-ttu-id="a4a36-123">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a4a36-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a36-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4a36-124">See Also</span></span>  
 [<span data-ttu-id="a4a36-125">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="a4a36-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="a4a36-126">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="a4a36-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="a4a36-127">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="a4a36-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="a4a36-128">Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="a4a36-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="a4a36-129">Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="a4a36-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="a4a36-130">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="a4a36-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="a4a36-131">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="a4a36-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
