---
title: Implementieren des MultipleView-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 292a1c0a57c992e847dd72a24508482cb6783121
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513600"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="e75a8-102">Implementieren des MultipleView-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e75a8-102">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="e75a8-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e75a8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e75a8-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="e75a8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e75a8-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, einschließlich Informationen über Ereignisse und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e75a8-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="e75a8-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e75a8-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="e75a8-107">Das <xref:System.Windows.Automation.MultipleViewPattern> -Steuerelementmuster dient zur Unterstützung von Steuerelementen, die mehrere Darstellungen desselben Satzes von Informationen oder untergeordneten Steuerelementen bereitstellt und zwischen diesen wechseln kann.</span><span class="sxs-lookup"><span data-stu-id="e75a8-107">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="e75a8-108">Beispiele für Steuerelemente, die mehrere Ansichten darstellen können, umfassen die Listenansicht (die den Inhalt als Miniaturansichten, Kacheln, Symbole oder Details anzeigen kann), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] -Diagramme (Kreis-, Linien- und Balkendiagramm sowie Zellwert mit Formel) [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] -Dokumente (Normal, Weblayout, Seitenlayout, Lesemoduslayout, Gliederung), [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] -Kalender (Jahr, Monat, Woche, Tag) und [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] -Skins.</span><span class="sxs-lookup"><span data-stu-id="e75a8-108">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] charts (pie, line, bar, cell value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] documents (normal, Web layout, print layout, reading layout, outline), [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)] calendar (year, month, week, day), and [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] skins.</span></span> <span data-ttu-id="e75a8-109">Die unterstützten Ansichten werden vom Steuerelemententwickler bestimmt und sind für jedes Steuerelement spezifisch.</span><span class="sxs-lookup"><span data-stu-id="e75a8-109">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="e75a8-110">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="e75a8-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="e75a8-111">Beachten Sie beim Implementieren des Steuerelementmusters für mehrere Ansichten die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="e75a8-111">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="e75a8-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> sollte auch für einen Container implementiert werden, der die aktuelle Ansicht verwaltet, wenn er sich von einem Steuerelement unterscheidet, das die aktuelle Ansicht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e75a8-112"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="e75a8-113">Windows Explorer enthält z. B. ein Listensteuerelement für den aktuellen Ordnerinhalt, während die Ansicht für das Steuerelement über die Windows Explorer-Anwendung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e75a8-113">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
-   <span data-ttu-id="e75a8-114">Ein Steuerelement, das seinen Inhalt sortieren kann, wird nicht als Steuerelement betrachtet, das mehrere Ansichten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e75a8-114">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
-   <span data-ttu-id="e75a8-115">Die Auflistung von Ansichten muss instanzenübergreifend identisch sein.</span><span class="sxs-lookup"><span data-stu-id="e75a8-115">The collection of views must be identical across instances.</span></span>  
  
-   <span data-ttu-id="e75a8-116">Die Namen von Ansichten müssen für die Sprachausgabe, Blindenschrift und andere lesbare Anwendungen geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="e75a8-116">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="e75a8-117">Erforderliche Member für IMultipleViewProvider</span><span class="sxs-lookup"><span data-stu-id="e75a8-117">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="e75a8-118">Die folgenden Eigenschaften und Methoden sind für das Implementieren von „IMultipleViewProvider“ erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e75a8-118">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="e75a8-119">Erforderliche Member</span><span class="sxs-lookup"><span data-stu-id="e75a8-119">Required members</span></span>|<span data-ttu-id="e75a8-120">Memberart</span><span class="sxs-lookup"><span data-stu-id="e75a8-120">Member type</span></span>|<span data-ttu-id="e75a8-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e75a8-121">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="e75a8-122">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e75a8-122">Property</span></span>|<span data-ttu-id="e75a8-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="e75a8-123">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="e75a8-124">Methode</span><span class="sxs-lookup"><span data-stu-id="e75a8-124">Method</span></span>|<span data-ttu-id="e75a8-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="e75a8-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="e75a8-126">Methode</span><span class="sxs-lookup"><span data-stu-id="e75a8-126">Method</span></span>|<span data-ttu-id="e75a8-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="e75a8-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="e75a8-128">Methode</span><span class="sxs-lookup"><span data-stu-id="e75a8-128">Method</span></span>|<span data-ttu-id="e75a8-129">Keiner</span><span class="sxs-lookup"><span data-stu-id="e75a8-129">None</span></span>|  
  
 <span data-ttu-id="e75a8-130">Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e75a8-130">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="e75a8-131">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e75a8-131">Exceptions</span></span>  
 <span data-ttu-id="e75a8-132">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="e75a8-132">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="e75a8-133">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="e75a8-133">Exception type</span></span>|<span data-ttu-id="e75a8-134">Bedingung</span><span class="sxs-lookup"><span data-stu-id="e75a8-134">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="e75a8-135">Wenn entweder <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> oder <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> mit einem Parameter aufgerufen wird, der kein Member der unterstützten Ansichtenauflistung ist.</span><span class="sxs-lookup"><span data-stu-id="e75a8-135">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e75a8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e75a8-136">See Also</span></span>  
 [<span data-ttu-id="e75a8-137">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e75a8-137">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="e75a8-138">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e75a8-138">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="e75a8-139">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="e75a8-139">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="e75a8-140">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="e75a8-140">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="e75a8-141">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="e75a8-141">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
