---
title: Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 4374666ba5e03720413614c63b00ba987f81f58f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447080"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="ddb75-102">Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ddb75-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="ddb75-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ddb75-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ddb75-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ddb75-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ddb75-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITableItemProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ddb75-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="ddb75-106">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ddb75-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="ddb75-107">Das <xref:System.Windows.Automation.TableItemPattern>-Steuerelementmuster wird verwendet, um untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.ITableProvider> implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="ddb75-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="ddb75-108">Zugriff auf Funktionen einzelner Zellen wird durch die gleichzeitig erforderliche Implementierung von <xref:System.Windows.Automation.Provider.IGridItemProvider> bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ddb75-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="ddb75-109">Dieses Steuerelementmuster ist analog zu <xref:System.Windows.Automation.Provider.IGridItemProvider> mit dem Unterschied, dass jedes Steuerelement, das <xref:System.Windows.Automation.Provider.ITableItemProvider> implementiert, programmgesteuert die Beziehung zwischen der einzelnen Zelle und deren Zeilen- und Spalteninformationen verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="ddb75-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="ddb75-110">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ddb75-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ddb75-111">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="ddb75-111">Implementation Guidelines and Conventions</span></span>  
  
- <span data-ttu-id="ddb75-112">Weitere Informationen zu verwandten Raster Elementen finden Sie unter [Implementieren des GridItem-Steuerelement Musters der Benutzeroberflächen Automatisierung](implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="ddb75-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="ddb75-113">Erforderliche Member für ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="ddb75-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="ddb75-114">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="ddb75-114">Required member</span></span>|<span data-ttu-id="ddb75-115">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="ddb75-115">Member type</span></span>|<span data-ttu-id="ddb75-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddb75-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="ddb75-117">Methode</span><span class="sxs-lookup"><span data-stu-id="ddb75-117">Method</span></span>|<span data-ttu-id="ddb75-118">Keine</span><span class="sxs-lookup"><span data-stu-id="ddb75-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="ddb75-119">Methode</span><span class="sxs-lookup"><span data-stu-id="ddb75-119">Method</span></span>|<span data-ttu-id="ddb75-120">Keine</span><span class="sxs-lookup"><span data-stu-id="ddb75-120">None</span></span>|  
  
 <span data-ttu-id="ddb75-121">Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ddb75-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="ddb75-122">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ddb75-122">Exceptions</span></span>  
 <span data-ttu-id="ddb75-123">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ddb75-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb75-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb75-124">See also</span></span>

- [<span data-ttu-id="ddb75-125">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ddb75-125">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ddb75-126">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ddb75-126">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ddb75-127">UI Automation Control Patterns for Clients</span><span class="sxs-lookup"><span data-stu-id="ddb75-127">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ddb75-128">Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ddb75-128">Implementing the UI Automation Table Control Pattern</span></span>](implementing-the-ui-automation-table-control-pattern.md)
- [<span data-ttu-id="ddb75-129">Implementieren des GridItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ddb75-129">Implementing the UI Automation GridItem Control Pattern</span></span>](implementing-the-ui-automation-griditem-control-pattern.md)
- [<span data-ttu-id="ddb75-130">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="ddb75-130">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ddb75-131">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ddb75-131">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
