---
title: Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Lesen Sie die Richtlinien und Konventionen zum Implementieren des Table-Steuerelement Musters in der Benutzeroberflächen Automatisierung Sie müssen erforderliche Member für die ITableProvider-Schnittstelle kennen.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 9c1d57e46aed9ec2441a95544d26244d2dfa9496
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265751"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="ccf27-104">Implementieren des Table-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ccf27-104">Implementing the UI Automation Table Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="ccf27-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ccf27-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ccf27-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="ccf27-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="ccf27-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITableProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="ccf27-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="ccf27-108">Links zu zusätzlichen Referenzen sind am Ende dieser Übersicht aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ccf27-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="ccf27-109">Das <xref:System.Windows.Automation.TablePattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die als Container für eine Auflistung von untergeordneten Elementen dienen.</span><span class="sxs-lookup"><span data-stu-id="ccf27-109">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="ccf27-110">Die untergeordneten Elemente dieses Elements müssen <xref:System.Windows.Automation.Provider.ITableItemProvider> implementieren und in einem zweidimensionalen logischen Koordinatensystem angeordnet sein, das zeilen- und spaltenweise durchlaufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ccf27-110">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="ccf27-111">Dieses Steuerelementmuster entspricht dem <xref:System.Windows.Automation.Provider.IGridProvider>, mit dem Unterschied, dass jedes <xref:System.Windows.Automation.Provider.ITableProvider> implementierende Steuerelement für jedes untergeordnete Element auch eine Beziehung zwischen Spalten- und/oder Zeilenüberschriften verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="ccf27-111">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="ccf27-112">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ccf27-112">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="ccf27-113">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="ccf27-113">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="ccf27-114">Beachten Sie beim Implementieren des Table-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="ccf27-114">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="ccf27-115">Der Zugriff auf den Inhalt der einzelnen Zellen erfolgt über ein zweidimensionales logisches Koordinatensystem oder über ein Array, das von der erforderlichen gleichzeitigen Implementierung von <xref:System.Windows.Automation.Provider.IGridProvider> bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ccf27-115">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
- <span data-ttu-id="ccf27-116">Eine Spalten- oder Zeilenüberschrift kann in einem Tabellenobjekt enthalten sein oder ein separates Headerobjekt darstellen, das einem Tabellenobjekt zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ccf27-116">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
- <span data-ttu-id="ccf27-117">Spalten- und Zeilenüberschriften können sowohl eine primäre als auch beliebige unterstützende Überschriften enthalten.</span><span class="sxs-lookup"><span data-stu-id="ccf27-117">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccf27-118">Dieses Konzept wird in einer Microsoft Excel-Tabelle ersichtlich, in der ein Benutzer eine "Vorname"-Spalte definiert hat.</span><span class="sxs-lookup"><span data-stu-id="ccf27-118">This concept becomes evident in a Microsoft Excel spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="ccf27-119">Diese Spalte verfügt jetzt über zwei Überschriften. Die vom Benutzer definierte Überschrift „Vorname“ und die alphanumerische Bezeichnung der Spalte, die von der Anwendung zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ccf27-119">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
- <span data-ttu-id="ccf27-120">Weitere Informationen finden Sie [unter Implementieren des Grid-Steuerelement Musters der Benutzeroberflächen Automatisierung](implementing-the-ui-automation-grid-control-pattern.md) .</span><span class="sxs-lookup"><span data-stu-id="ccf27-120">See [Implementing the UI Automation Grid Control Pattern](implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="ccf27-121">![Tabelle mit komplexen Headerelementen](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="ccf27-121">![Table with complex header items.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="ccf27-122">Beispiel für eine Tabelle mit komplexen Spaltenüberschriften</span><span class="sxs-lookup"><span data-stu-id="ccf27-122">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="ccf27-123">![Tabelle mit mehrdeutiger RowOrColumnMajor-Eigenschaft.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="ccf27-123">![Table with ambiguous RowOrColumnMajor property.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="ccf27-124">Beispiel für eine Tabelle mit mehrdeutiger RowOrColumnMajor-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ccf27-124">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>

## <a name="required-members-for-itableprovider"></a><span data-ttu-id="ccf27-125">Erforderliche Member für ITableProvider</span><span class="sxs-lookup"><span data-stu-id="ccf27-125">Required Members for ITableProvider</span></span>  

 <span data-ttu-id="ccf27-126">Für die ITableProvider-Schnittstelle werden die folgenden Eigenschaften und Methoden benötigt.</span><span class="sxs-lookup"><span data-stu-id="ccf27-126">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="ccf27-127">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="ccf27-127">Required members</span></span>|<span data-ttu-id="ccf27-128">Memberart</span><span class="sxs-lookup"><span data-stu-id="ccf27-128">Member type</span></span>|<span data-ttu-id="ccf27-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ccf27-129">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="ccf27-130">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ccf27-130">Property</span></span>|<span data-ttu-id="ccf27-131">Keine</span><span class="sxs-lookup"><span data-stu-id="ccf27-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="ccf27-132">Methode</span><span class="sxs-lookup"><span data-stu-id="ccf27-132">Method</span></span>|<span data-ttu-id="ccf27-133">Keine</span><span class="sxs-lookup"><span data-stu-id="ccf27-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="ccf27-134">Methode</span><span class="sxs-lookup"><span data-stu-id="ccf27-134">Method</span></span>|<span data-ttu-id="ccf27-135">Keine</span><span class="sxs-lookup"><span data-stu-id="ccf27-135">None</span></span>|  
  
 <span data-ttu-id="ccf27-136">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ccf27-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="ccf27-137">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="ccf27-137">Exceptions</span></span>  

 <span data-ttu-id="ccf27-138">Diesem Steuerelementmuster sind keine Ausnahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ccf27-138">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf27-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccf27-139">See also</span></span>

- [<span data-ttu-id="ccf27-140">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ccf27-140">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="ccf27-141">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ccf27-141">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="ccf27-142">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="ccf27-142">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="ccf27-143">Implementieren des TableItem-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ccf27-143">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="ccf27-144">Implementieren des Grid-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ccf27-144">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="ccf27-145">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="ccf27-145">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="ccf27-146">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="ccf27-146">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
