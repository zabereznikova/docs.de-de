---
title: Implementieren des RangeValue-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Lesen Sie die Richtlinien und Konventionen zum Implementieren des RangeValue-Steuerelement Musters in der Benutzeroberflächen Automatisierung. Weitere Informationen finden Sie unter Erforderliche Member für die IRangeValueProvider-Schnittstelle.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: 9b5bfd571b078b7aeab149f5371004ac832fadcc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239561"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="e65cf-104">Implementieren des RangeValue-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e65cf-104">Implementing the UI Automation RangeValue Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="e65cf-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e65cf-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e65cf-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e65cf-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e65cf-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IRangeValueProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e65cf-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="e65cf-108">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e65cf-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="e65cf-109">Das <xref:System.Windows.Automation.RangeValuePattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die auf einen Wert innerhalb eines Bereichs festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="e65cf-109">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="e65cf-110">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e65cf-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="e65cf-111">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="e65cf-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="e65cf-112">Beachten Sie beim Implementieren des RangeValue-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="e65cf-112">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="e65cf-113">Steuerelemente lassen eine erneute Kalibrierung der unterstützten Eigenschaften auf Grundlage des Gebietsschemas oder einer Benutzereinstellung zu.</span><span class="sxs-lookup"><span data-stu-id="e65cf-113">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="e65cf-114">Ein Beispiel hierfür ist ein Thermometersteuerelement, das so festgelegt werden kann, dass die Temperatur in Fahrenheit oder Celsius angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e65cf-114">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="e65cf-115">Für Steuerelemente, die über mehrdeutige Bereichswerte verfügen, z. B. Statusanzeigen oder Schieberegler, sollten diese Werte normalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e65cf-115">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="e65cf-116">![Statusanzeige.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="e65cf-116">![Progress bar.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="e65cf-117">Beispiel für eine Statusanzeige, in der der Wert eine ganze Zahl ist und die minimalen und maximalen Eigenschaftswerte auf 0 (null) beziehungsweise 100 normalisiert werden</span><span class="sxs-lookup"><span data-stu-id="e65cf-117">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>

## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="e65cf-118">Erforderliche Member für „IRangeValueProvider“</span><span class="sxs-lookup"><span data-stu-id="e65cf-118">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="e65cf-119">Erforderlicher Member</span><span class="sxs-lookup"><span data-stu-id="e65cf-119">Required member</span></span>|<span data-ttu-id="e65cf-120">Memberart</span><span class="sxs-lookup"><span data-stu-id="e65cf-120">Member type</span></span>|<span data-ttu-id="e65cf-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e65cf-121">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="e65cf-122">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e65cf-122">Property</span></span>|<span data-ttu-id="e65cf-123">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="e65cf-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e65cf-124">Property</span></span>|<span data-ttu-id="e65cf-125">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="e65cf-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e65cf-126">Property</span></span>|<span data-ttu-id="e65cf-127">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="e65cf-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e65cf-128">Property</span></span>|<span data-ttu-id="e65cf-129">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="e65cf-130">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e65cf-130">Property</span></span>|<span data-ttu-id="e65cf-131">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="e65cf-132">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e65cf-132">Property</span></span>|<span data-ttu-id="e65cf-133">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-133">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="e65cf-134">Methoden</span><span class="sxs-lookup"><span data-stu-id="e65cf-134">Methods</span></span>|<span data-ttu-id="e65cf-135">Keine</span><span class="sxs-lookup"><span data-stu-id="e65cf-135">None</span></span>|  
  
 <span data-ttu-id="e65cf-136">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e65cf-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="e65cf-137">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e65cf-137">Exceptions</span></span>  

 <span data-ttu-id="e65cf-138">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="e65cf-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="e65cf-139">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="e65cf-139">Exception type</span></span>|<span data-ttu-id="e65cf-140">Bedingung</span><span class="sxs-lookup"><span data-stu-id="e65cf-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="e65cf-141"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> wird mit einem Wert aufgerufen, der entweder größer als <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> oder kleiner als <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>ist.</span><span class="sxs-lookup"><span data-stu-id="e65cf-141"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e65cf-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e65cf-142">See also</span></span>

- [<span data-ttu-id="e65cf-143">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e65cf-143">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="e65cf-144">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e65cf-144">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="e65cf-145">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="e65cf-145">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="e65cf-146">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="e65cf-146">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="e65cf-147">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e65cf-147">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
