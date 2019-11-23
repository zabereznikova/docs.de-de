---
title: Implementieren des MultipleView-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: c9199e0ea1971c22bfc1f6334b9d2d9d73bb048c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435056"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="0d602-102">Implementieren des MultipleView-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="0d602-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="0d602-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0d602-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0d602-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="0d602-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="0d602-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0d602-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="0d602-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="0d602-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="0d602-107">Das <xref:System.Windows.Automation.MultipleViewPattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die mehrere Darstellungen desselben Satzes von Informationen oder untergeordneten Steuerelementen bereitstellt und zwischen diesen wechseln kann.</span><span class="sxs-lookup"><span data-stu-id="0d602-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="0d602-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span><span class="sxs-lookup"><span data-stu-id="0d602-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="0d602-109">Die unterstützten Ansichten werden vom Steuerelemententwickler bestimmt und sind für jedes Steuerelement spezifisch.</span><span class="sxs-lookup"><span data-stu-id="0d602-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="0d602-110">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="0d602-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="0d602-111">Beachten Sie beim Implementieren des Steuerelementmusters für mehrere Ansichten die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="0d602-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="0d602-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> sollte auch für einen Container implementiert werden, der die aktuelle Ansicht verwaltet, wenn er sich von einem Steuerelement unterscheidet, das die aktuelle Ansicht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0d602-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="0d602-113">Windows Explorer enthält z. B. ein Listensteuerelement für den aktuellen Ordnerinhalt, während die Ansicht für das Steuerelement über die Windows Explorer-Anwendung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0d602-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="0d602-114">Ein Steuerelement, das seinen Inhalt sortieren kann, wird nicht als Steuerelement betrachtet, das mehrere Ansichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0d602-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="0d602-115">Die Auflistung von Ansichten muss instanzenübergreifend identisch sein.</span><span class="sxs-lookup"><span data-stu-id="0d602-115">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="0d602-116">Die Namen von Ansichten müssen für die Sprachausgabe, Blindenschrift und andere lesbare Anwendungen geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="0d602-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="0d602-117">Erforderliche Member für IMultipleViewProvider</span><span class="sxs-lookup"><span data-stu-id="0d602-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="0d602-118">Die folgenden Eigenschaften und Methoden sind für das Implementieren von „IMultipleViewProvider“ erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d602-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="0d602-119">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="0d602-119">Required members</span></span>|<span data-ttu-id="0d602-120">Memberart</span><span class="sxs-lookup"><span data-stu-id="0d602-120">Member type</span></span>|<span data-ttu-id="0d602-121">Notizen</span><span class="sxs-lookup"><span data-stu-id="0d602-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="0d602-122">property</span><span class="sxs-lookup"><span data-stu-id="0d602-122">Property</span></span>|<span data-ttu-id="0d602-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="0d602-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="0d602-124">Methode</span><span class="sxs-lookup"><span data-stu-id="0d602-124">Method</span></span>|<span data-ttu-id="0d602-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="0d602-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="0d602-126">Methode</span><span class="sxs-lookup"><span data-stu-id="0d602-126">Method</span></span>|<span data-ttu-id="0d602-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="0d602-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="0d602-128">Methode</span><span class="sxs-lookup"><span data-stu-id="0d602-128">Method</span></span>|<span data-ttu-id="0d602-129">Keiner</span><span class="sxs-lookup"><span data-stu-id="0d602-129">None</span></span>|  
  
 <span data-ttu-id="0d602-130">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0d602-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="0d602-131">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="0d602-131">Exceptions</span></span>  
 <span data-ttu-id="0d602-132">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="0d602-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="0d602-133">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="0d602-133">Exception type</span></span>|<span data-ttu-id="0d602-134">Bedingung</span><span class="sxs-lookup"><span data-stu-id="0d602-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="0d602-135">Wenn entweder <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> oder <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> mit einem Parameter aufgerufen wird, der kein Member der unterstützten Ansichtenauflistung ist.</span><span class="sxs-lookup"><span data-stu-id="0d602-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d602-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d602-136">See also</span></span>

- [<span data-ttu-id="0d602-137">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="0d602-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="0d602-138">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0d602-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="0d602-139">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="0d602-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="0d602-140">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="0d602-140">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="0d602-141">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="0d602-141">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
