---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften
description: Eine umfassende Übersicht über die Eigenschaften der Microsoft UI-Automatisierung finden Sie unter. Weitere Informationen zu Eigenschafts bezeichmern, Eigenschaften nach Kategorie, Lokalisierung und Eigenschaften und Ereignissen.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 95729c1d26a9ae7fdec4fa4215f9478251612242
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240393"
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="851e5-104">Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="851e5-104">UI Automation Properties Overview</span></span>

> [!NOTE]
> <span data-ttu-id="851e5-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="851e5-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="851e5-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="851e5-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="851e5-107">Benutzeroberflächenautomatisierungs-Anbieter machen Eigenschaften von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Elementen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="851e5-107">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="851e5-108">Diese Eigenschaften ermöglichen es Benutzeroberflächenautomatisierungs-Clientanwendungen, Informationen zu Bestandteilen der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)](insbesondere Steuerelemente) zu ermitteln, wobei diese Informationen sowohl statische als auch dynamische Daten umfassen können.</span><span class="sxs-lookup"><span data-stu-id="851e5-108">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="851e5-109">In diesem Abschnitt finden Sie eine allgemeine Übersicht über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="851e5-109">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="851e5-110">Speziellere Informationen finden Sie in folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="851e5-110">More specific information is given in the following topics:</span></span>  
  
- [<span data-ttu-id="851e5-111">Benutzeroberflächenautomatisierungs-Eigenschaften für Clients</span><span class="sxs-lookup"><span data-stu-id="851e5-111">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)  
  
- [<span data-ttu-id="851e5-112">Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="851e5-112">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>

## <a name="property-identifiers"></a><span data-ttu-id="851e5-113">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-113">Property Identifiers</span></span>  

 <span data-ttu-id="851e5-114">Jede Eigenschaft wird mit einer Zahl und einem Namen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="851e5-114">Every property is identified by a number and a name.</span></span> <span data-ttu-id="851e5-115">Die Namen von Eigenschaften werden nur zum Debuggen und zu Diagnosezwecken verwendet.</span><span class="sxs-lookup"><span data-stu-id="851e5-115">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="851e5-116">Anbieter verwenden die numerischen IDs, um eingehende Eigenschaften Anforderungen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="851e5-116">Providers use the numeric IDs to identify incoming property requests.</span></span> <span data-ttu-id="851e5-117">Clientanwendungen verwenden dagegen, um die abzurufenden Eigenschaften zu kennzeichnen, nur <xref:System.Windows.Automation.AutomationProperty>-Objekte, in denen die Zahl und der Name gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="851e5-117">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="851e5-118"><xref:System.Windows.Automation.AutomationProperty> -Objekte, die bestimmte Eigenschaften darstellen, sind als Felder in verschiedenen Klassen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="851e5-118"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="851e5-119">Aus Sicherheitsgründen rufen Benutzeroberflächenautomatisierungs-Anbieter diese Objekte aus einem separaten Satz von Klassen ab, die in „Uiautomationtypes.dll“ enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="851e5-119">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="851e5-120">In der folgenden Tabelle werden die Eigenschaften durch die Klassen, die die IDs enthalten, kategorisiert <xref:System.Windows.Automation.AutomationProperty> .</span><span class="sxs-lookup"><span data-stu-id="851e5-120">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>IDs.</span></span>  
  
|<span data-ttu-id="851e5-121">Arten von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="851e5-121">Kinds of properties</span></span>|<span data-ttu-id="851e5-122">Clients rufen IDs ab von</span><span class="sxs-lookup"><span data-stu-id="851e5-122">Clients get IDs from</span></span>|<span data-ttu-id="851e5-123">Anbieter rufen IDs ab von</span><span class="sxs-lookup"><span data-stu-id="851e5-123">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="851e5-124">Eigenschaften, die jedes der Elemente hat (siehe folgende Tabellen)</span><span class="sxs-lookup"><span data-stu-id="851e5-124">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="851e5-125">Position eines andockbaren Fensters</span><span class="sxs-lookup"><span data-stu-id="851e5-125">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="851e5-126">Zustand eines Elements, das erweitert und reduziert werden kann</span><span class="sxs-lookup"><span data-stu-id="851e5-126">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="851e5-127">Eigenschaften eines Elements in einem Raster</span><span class="sxs-lookup"><span data-stu-id="851e5-127">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="851e5-128">Eigenschaften eines Rasters</span><span class="sxs-lookup"><span data-stu-id="851e5-128">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="851e5-129">Aktuelle und unterstützte Ansicht eines Elements, das mehrere Ansichten hat</span><span class="sxs-lookup"><span data-stu-id="851e5-129">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="851e5-130">Eigenschaften eines Elements, das innerhalb eines Wertebereichs verschoben werden kann, etwa ein Schieberegler</span><span class="sxs-lookup"><span data-stu-id="851e5-130">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="851e5-131">Eigenschaften eines scrollbaren Fensters</span><span class="sxs-lookup"><span data-stu-id="851e5-131">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="851e5-132">Status und Container eines Elements, das ausgewählt werden kann, z. B. in einer Liste</span><span class="sxs-lookup"><span data-stu-id="851e5-132">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="851e5-133">Eigenschaften eines Steuerelements, das Auswahlelemente enthält</span><span class="sxs-lookup"><span data-stu-id="851e5-133">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="851e5-134">Spalten- und Zeilenüberschriften eines Elements in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="851e5-134">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="851e5-135">Spalten- und Zeilenüberschriften sowie Ausrichtung einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="851e5-135">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="851e5-136">Zustand eines umschaltbaren Steuerelements</span><span class="sxs-lookup"><span data-stu-id="851e5-136">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="851e5-137">Funktionen eines Elements, das verschoben, gedreht oder in der Größe geändert werden kann</span><span class="sxs-lookup"><span data-stu-id="851e5-137">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="851e5-138">Wert und Lese-/Schreibfunktionen eines Elements, das einen Wert hat</span><span class="sxs-lookup"><span data-stu-id="851e5-138">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="851e5-139">Funktionen und Status eines Fensters</span><span class="sxs-lookup"><span data-stu-id="851e5-139">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>

## <a name="properties-by-category"></a><span data-ttu-id="851e5-140">Eigenschaften nach Kategorie</span><span class="sxs-lookup"><span data-stu-id="851e5-140">Properties by Category</span></span>  

 <span data-ttu-id="851e5-141">In den folgenden Tabellen sind die Eigenschaften kategorisiert, deren IDs in und enthalten sind <xref:System.Windows.Automation.AutomationElement> <xref:System.Windows.Automation.AutomationElementIdentifiers> .</span><span class="sxs-lookup"><span data-stu-id="851e5-141">The following tables categorize the properties whose IDs are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="851e5-142">Diese Eigenschaften hat jedes der Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="851e5-142">These properties are common to all controls.</span></span> <span data-ttu-id="851e5-143">Bis auf einige Ausnahmen sind wahrscheinlich alle diese Eigenschaften während der gesamten Lebensdauer der Anbieteranwendung statisch. Die meisten dynamischen Eigenschaften sind mit Steuerelementmustern verknüpft.</span><span class="sxs-lookup"><span data-stu-id="851e5-143">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="851e5-144">In der Spalte **Eigenschaftenzugriff** werden zusätzlich zu <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> und <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>alle weiteren Accessoren für jede Eigenschaft aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="851e5-144">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="851e5-145">Weitere Informationen zum Abrufen von Eigenschaften in einer Clientanwendung finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="851e5-145">For more information on getting properties in a client application, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="851e5-146">Spezielle Informationen zu jeder Eigenschaft finden Sie über den Link in der Spalte **Eigenschaftenzugriff** .</span><span class="sxs-lookup"><span data-stu-id="851e5-146">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="851e5-147">Anzeigen von Merkmalen</span><span class="sxs-lookup"><span data-stu-id="851e5-147">Display Characteristics</span></span>  
  
|<span data-ttu-id="851e5-148">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-148">Property identifier</span></span>|<span data-ttu-id="851e5-149">Eigenschaftenzugriff</span><span class="sxs-lookup"><span data-stu-id="851e5-149">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="851e5-150">–</span><span class="sxs-lookup"><span data-stu-id="851e5-150">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="851e5-151">Elementtyp</span><span class="sxs-lookup"><span data-stu-id="851e5-151">Element Type</span></span>  
  
|<span data-ttu-id="851e5-152">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-152">Property identifier</span></span>|<span data-ttu-id="851e5-153">Eigenschaftenzugriff</span><span class="sxs-lookup"><span data-stu-id="851e5-153">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="851e5-154">Identifikation</span><span class="sxs-lookup"><span data-stu-id="851e5-154">Identification</span></span>  
  
|<span data-ttu-id="851e5-155">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-155">Property identifier</span></span>|<span data-ttu-id="851e5-156">Eigenschaftenzugriff</span><span class="sxs-lookup"><span data-stu-id="851e5-156">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="851e5-157">Interaktion</span><span class="sxs-lookup"><span data-stu-id="851e5-157">Interaction</span></span>  
  
|<span data-ttu-id="851e5-158">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-158">Property identifier</span></span>|<span data-ttu-id="851e5-159">Eigenschaftenzugriff</span><span class="sxs-lookup"><span data-stu-id="851e5-159">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="851e5-160">Unterstützung für Muster</span><span class="sxs-lookup"><span data-stu-id="851e5-160">Support for Patterns</span></span>  
  
|<span data-ttu-id="851e5-161">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-161">Property identifier</span></span>|<span data-ttu-id="851e5-162">Eigenschaftenzugriff</span><span class="sxs-lookup"><span data-stu-id="851e5-162">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="851e5-163">Sonstiges</span><span class="sxs-lookup"><span data-stu-id="851e5-163">Miscellaneous</span></span>  
  
|<span data-ttu-id="851e5-164">Eigenschaftsbezeichner</span><span class="sxs-lookup"><span data-stu-id="851e5-164">Property identifier</span></span>|<span data-ttu-id="851e5-165">Eigenschaftenzugriff</span><span class="sxs-lookup"><span data-stu-id="851e5-165">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>

## <a name="localization"></a><span data-ttu-id="851e5-166">Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="851e5-166">Localization</span></span>  

 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="851e5-167">-Anbieter sollten folgende Eigenschaften in der Sprache des Betriebssystems zur Verfügung stellen:</span><span class="sxs-lookup"><span data-stu-id="851e5-167">providers should present the following properties in the language of the operating system:</span></span>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>

## <a name="properties-and-events"></a><span data-ttu-id="851e5-168">Eigenschaften und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="851e5-168">Properties and Events</span></span>  

 <span data-ttu-id="851e5-169">Direkt verknüpft mit den Eigenschaften in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist das Konzept von Ereignissen aufgrund von geänderten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="851e5-169">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="851e5-170">Bei dynamischen Eigenschaften muss die Clientanwendung feststellen können, ob ein Eigenschaftswert geändert wurde. Nur dann kann sie die Informationen in ihrem Cache aktualisieren oder auf andere Weise auf die neuen Informationen reagieren.</span><span class="sxs-lookup"><span data-stu-id="851e5-170">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="851e5-171">Anbieter lösen Ereignisse aus, wenn irgendetwas in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="851e5-171">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="851e5-172">Wird zum Beispiel ein Kontrollkästchen aktiviert oder deaktiviert, wird von dem Umschaltmuster, das für den Anbieter implementiert ist, ein Ereignis entsprechend der Eigenschaftenänderung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="851e5-172">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="851e5-173">Anbieter können abhängig davon, ob Clients Ereignissen oder bestimmten Ereignissen lauschen, selektiv Ereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="851e5-173">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="851e5-174">Es werden nicht für alle Eigenschaftenänderung Ereignisse ausgelöst. Dies ist vollständig von der Implementierung des Benutzeroberflächenautomatisierungs-Anbieters für das Element abhängig.</span><span class="sxs-lookup"><span data-stu-id="851e5-174">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="851e5-175">Die Standardproxyanbieter für Listenfelder lösen beispielsweise kein Ereignis aus, wenn <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> geändert wird.</span><span class="sxs-lookup"><span data-stu-id="851e5-175">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="851e5-176">In diesem Fall muss die Anwendung einem <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>lauschen.</span><span class="sxs-lookup"><span data-stu-id="851e5-176">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="851e5-177">Clients lauschen Ereignissen, indem sie diese abonnieren.</span><span class="sxs-lookup"><span data-stu-id="851e5-177">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="851e5-178">Abonnieren von Ereignissen bedeutet, dass Delegatenmethoden erstellt werden, die Ereignisse verarbeiten können, und dass die Methoden anschließend zusammen mit den Ereignissen, die von diesen Methoden verarbeitet werden, an [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="851e5-178">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="851e5-179">Insbesondere für Ereignisse wegen geänderter Eigenschaften müssen Clients <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>implementieren.</span><span class="sxs-lookup"><span data-stu-id="851e5-179">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="851e5-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="851e5-180">See also</span></span>

- [<span data-ttu-id="851e5-181">Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients</span><span class="sxs-lookup"><span data-stu-id="851e5-181">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
- [<span data-ttu-id="851e5-182">Benutzeroberflächenautomatisierungs-Eigenschaften für Clients</span><span class="sxs-lookup"><span data-stu-id="851e5-182">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="851e5-183">Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="851e5-183">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
- [<span data-ttu-id="851e5-184">Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung</span><span class="sxs-lookup"><span data-stu-id="851e5-184">Find a UI Automation Element Based on a Property Condition</span></span>](find-a-ui-automation-element-based-on-a-property-condition.md)
- [<span data-ttu-id="851e5-185">Zurückgeben von Eigenschaften aus einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="851e5-185">Return Properties from a UI Automation Provider</span></span>](return-properties-from-a-ui-automation-provider.md)
- [<span data-ttu-id="851e5-186">Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="851e5-186">Raise Events from a UI Automation Provider</span></span>](raise-events-from-a-ui-automation-provider.md)
