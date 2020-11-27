---
title: Implementieren des Transform-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Überprüfen Sie die Richtlinien und Konventionen zum Implementieren des Transformations Steuerungs Musters in der Benutzeroberflächen Automatisierung. Sie müssen erforderliche Member für die ITransformProvider-Schnittstelle kennen.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: fc47170a08ff08f6cd8f67996ef8fbf19c40f819
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265647"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a><span data-ttu-id="e641e-104">Implementieren des Transform-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e641e-104">Implementing the UI Automation Transform Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="e641e-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e641e-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e641e-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e641e-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e641e-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ITransformProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="e641e-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="e641e-108">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e641e-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="e641e-109">Das <xref:System.Windows.Automation.TransformPattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die in einem zweidimensionalen Raum verschoben, verkleinert, vergrößert oder gedreht werden können.</span><span class="sxs-lookup"><span data-stu-id="e641e-109">The <xref:System.Windows.Automation.TransformPattern> control pattern is used to support controls that can be moved, resized, or rotated within a two-dimensional space.</span></span> <span data-ttu-id="e641e-110">Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e641e-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="e641e-111">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="e641e-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="e641e-112">Beachten Sie beim Implementieren des Transform-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="e641e-112">When implementing the Transform control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="e641e-113">Die Unterstützung für dieses Steuerelementmuster ist nicht auf Objekte auf dem Desktop beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e641e-113">Support for this control pattern is not limited to objects on the desktop.</span></span> <span data-ttu-id="e641e-114">Dieses Steuerelementmuster muss auch von den untergeordneten Elementen eines Containerobjekts unterstützt werden, wenn die untergeordneten Elemente verschoben, vergrößert, verkleinert oder innerhalb der Grenzen des Containers frei gedreht werden können.</span><span class="sxs-lookup"><span data-stu-id="e641e-114">This control pattern must also be supported by the children of a container object if the children can be moved, resized, or rotated freely within the boundaries of the container.</span></span>  
  
- <span data-ttu-id="e641e-115">Ein Objekt kann nicht so verschoben, vergrößert, verkleinert oder gedreht werden, dass seine resultierende Bildschirmposition vollständig außerhalb der Koordinaten des Containers liegt und daher nicht über die Tastatur oder Maus zugänglich ist (wenn z. B. ein Fenster auf oberster Ebene außerhalb des Bildschirms oder ein untergeordnetes Objekt außerhalb der Viewportgrenzen des Containers verschoben wird).</span><span class="sxs-lookup"><span data-stu-id="e641e-115">An object cannot be moved, resized, or rotated such that its resulting screen location would be completely outside the coordinates of its container and therefore inaccessible to the keyboard or mouse (for example, when a top-level window is moved off-screen or a child object is moved outside the boundaries of the container's viewport).</span></span> <span data-ttu-id="e641e-116">In diesen Fällen wird das Objekt so nahe wie möglich bei den angeforderten Bildschirmkoordinaten platziert, wobei die oberen oder linken Koordinaten außer Kraft gesetzt werden, damit sich die Koordinaten innerhalb der Containergrenzen befinden.</span><span class="sxs-lookup"><span data-stu-id="e641e-116">In these cases, the object is placed as close to the requested screen coordinates as possible with the top or left coordinates overridden to be within the container boundaries.</span></span>  
  
- <span data-ttu-id="e641e-117">Für Systeme mit mehreren Monitoren wird ein Objekt so nahe wie möglich bei den angeforderten Koordinaten auf dem primären Monitor platziert, wenn das Objekt vollständig außerhalb der Bildschirmkoordinaten des kombinierten Desktops verschoben, vergrößert, verkleinert oder gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="e641e-117">For multi-monitor systems, if an object is moved, resized, or rotated completely outside the combined desktop screen coordinates, the object is placed on the primary monitor as close to the requested coordinates as possible.</span></span>  
  
- <span data-ttu-id="e641e-118">Alle Parameter und Eigenschaftswerte sind absolute Angaben und unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="e641e-118">All parameters and property values are absolute and independent of locale.</span></span>  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-itransformprovider"></a><span data-ttu-id="e641e-119">Erforderliche Member für ITransformProvider</span><span class="sxs-lookup"><span data-stu-id="e641e-119">Required Members for ITransformProvider</span></span>  

 <span data-ttu-id="e641e-120">Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.ITransformProvider>erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e641e-120">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.ITransformProvider>.</span></span>  
  
|<span data-ttu-id="e641e-121">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="e641e-121">Required members</span></span>|<span data-ttu-id="e641e-122">Memberart</span><span class="sxs-lookup"><span data-stu-id="e641e-122">Member type</span></span>|<span data-ttu-id="e641e-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e641e-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|<span data-ttu-id="e641e-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e641e-124">Property</span></span>|<span data-ttu-id="e641e-125">Keine</span><span class="sxs-lookup"><span data-stu-id="e641e-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|<span data-ttu-id="e641e-126">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e641e-126">Property</span></span>|<span data-ttu-id="e641e-127">Keine</span><span class="sxs-lookup"><span data-stu-id="e641e-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|<span data-ttu-id="e641e-128">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e641e-128">Property</span></span>|<span data-ttu-id="e641e-129">Keine</span><span class="sxs-lookup"><span data-stu-id="e641e-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|<span data-ttu-id="e641e-130">Methode</span><span class="sxs-lookup"><span data-stu-id="e641e-130">Method</span></span>|<span data-ttu-id="e641e-131">Keine</span><span class="sxs-lookup"><span data-stu-id="e641e-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|<span data-ttu-id="e641e-132">Methode</span><span class="sxs-lookup"><span data-stu-id="e641e-132">Method</span></span>|<span data-ttu-id="e641e-133">Keine</span><span class="sxs-lookup"><span data-stu-id="e641e-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|<span data-ttu-id="e641e-134">Methode</span><span class="sxs-lookup"><span data-stu-id="e641e-134">Method</span></span>|<span data-ttu-id="e641e-135">Keine</span><span class="sxs-lookup"><span data-stu-id="e641e-135">None</span></span>|  
  
 <span data-ttu-id="e641e-136">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e641e-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="e641e-137">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e641e-137">Exceptions</span></span>  

 <span data-ttu-id="e641e-138">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="e641e-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="e641e-139">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="e641e-139">Exception Type</span></span>|<span data-ttu-id="e641e-140">Bedingung</span><span class="sxs-lookup"><span data-stu-id="e641e-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> <span data-ttu-id="e641e-141">-Wenn <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> false ist.</span><span class="sxs-lookup"><span data-stu-id="e641e-141">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> <span data-ttu-id="e641e-142">-Wenn <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> false ist.</span><span class="sxs-lookup"><span data-stu-id="e641e-142">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> is false.</span></span>|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> <span data-ttu-id="e641e-143">-Wenn <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> false ist.</span><span class="sxs-lookup"><span data-stu-id="e641e-143">-   If the <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> is false.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e641e-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e641e-144">See also</span></span>

- [<span data-ttu-id="e641e-145">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e641e-145">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="e641e-146">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e641e-146">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="e641e-147">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="e641e-147">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="e641e-148">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="e641e-148">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="e641e-149">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e641e-149">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
