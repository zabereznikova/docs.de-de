---
title: "Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 9e8d83c3ef40ccc6e97ba3128cab5d88a5af5305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="afe98-102">Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="afe98-102">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="afe98-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="afe98-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="afe98-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="afe98-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="afe98-105">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IWindowProvider>, einschließlich Informationen über <xref:System.Windows.Automation.WindowPattern> -Eigenschaften, -Methoden und -Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="afe98-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="afe98-106">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="afe98-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="afe98-107">Das <xref:System.Windows.Automation.WindowPattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die grundlegende fensterbasierte Funktionen in einer herkömmlichen [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="afe98-107">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)].</span></span> <span data-ttu-id="afe98-108">Beispiele für Steuerelemente, für die dieses Steuerelementmuster implementiert werden muss, sind Anwendungsfenster der obersten Ebene, untergeordnete [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] -Fenster, Teilbereichs-Steuerelemente, deren Größe geändert werden kann, modale Dialogfelder und Hilfefenster in Sprechblasenform.</span><span class="sxs-lookup"><span data-stu-id="afe98-108">Examples of controls that must implement this control pattern include top-level application windows, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="afe98-109">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="afe98-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="afe98-110">Beachten Sie beim Implementieren des Window-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="afe98-110">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="afe98-111">Damit ein Steuerelement in der Lage ist, Fenstergröße und Bildschirmposition über Benutzeroberflächenautomatisierung zu ändern, muss es <xref:System.Windows.Automation.Provider.ITransformProvider> zusätzlich zu <xref:System.Windows.Automation.Provider.IWindowProvider>implementieren.</span><span class="sxs-lookup"><span data-stu-id="afe98-111">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="afe98-112">Für Steuerelemente, die Titelleisten und Titelleistenelemente enthalten, mit denen das Steuerelement verschoben, maximiert, minimiert, geschlossen oder in der Größe verändert werden kann, muss üblicherweise <xref:System.Windows.Automation.Provider.IWindowProvider>implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="afe98-112">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="afe98-113">Für Steuerelemente wie QuickInfo-Popups und Dropdown-Kombinationsfelder oder -Menüs muss <xref:System.Windows.Automation.Provider.IWindowProvider>normalerweise nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="afe98-113">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="afe98-114">Hilfefenster in Sprechblasenform unterscheiden sich von normalen QuickInfo-Popups darin, dass sie eine wie für Fenster verwendete Schaltfläche zum Schließen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="afe98-114">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
-   <span data-ttu-id="afe98-115">Der Vollbildmodus wird von IWindowProvider nicht unterstützt, da er featurespezifisch für eine Anwendung und kein typisches Fensterverhalten ist.</span><span class="sxs-lookup"><span data-stu-id="afe98-115">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="afe98-116">Erforderliche Member für IWindowProvider</span><span class="sxs-lookup"><span data-stu-id="afe98-116">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="afe98-117">Die folgenden Eigenschaften, Methoden und Ereignisse sind für die IWindowProvider-Schnittstelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afe98-117">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="afe98-118">Erforderlicher Member</span><span class="sxs-lookup"><span data-stu-id="afe98-118">Required member</span></span>|<span data-ttu-id="afe98-119">Memberart</span><span class="sxs-lookup"><span data-stu-id="afe98-119">Member type</span></span>|<span data-ttu-id="afe98-120">Notizen</span><span class="sxs-lookup"><span data-stu-id="afe98-120">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="afe98-121">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="afe98-121">Property</span></span>|<span data-ttu-id="afe98-122">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="afe98-123">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="afe98-123">Property</span></span>|<span data-ttu-id="afe98-124">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="afe98-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="afe98-125">Property</span></span>|<span data-ttu-id="afe98-126">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="afe98-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="afe98-127">Property</span></span>|<span data-ttu-id="afe98-128">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="afe98-129">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="afe98-129">Property</span></span>|<span data-ttu-id="afe98-130">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="afe98-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="afe98-131">Property</span></span>|<span data-ttu-id="afe98-132">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="afe98-133">Methode</span><span class="sxs-lookup"><span data-stu-id="afe98-133">Method</span></span>|<span data-ttu-id="afe98-134">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="afe98-135">Methode</span><span class="sxs-lookup"><span data-stu-id="afe98-135">Method</span></span>|<span data-ttu-id="afe98-136">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="afe98-137">Methode</span><span class="sxs-lookup"><span data-stu-id="afe98-137">Method</span></span>|<span data-ttu-id="afe98-138">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-138">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="afe98-139">Ereignis</span><span class="sxs-lookup"><span data-stu-id="afe98-139">Event</span></span>|<span data-ttu-id="afe98-140">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="afe98-141">Ereignis</span><span class="sxs-lookup"><span data-stu-id="afe98-141">Event</span></span>|<span data-ttu-id="afe98-142">Keine</span><span class="sxs-lookup"><span data-stu-id="afe98-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="afe98-143">Ereignis</span><span class="sxs-lookup"><span data-stu-id="afe98-143">Event</span></span>|<span data-ttu-id="afe98-144"><xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="afe98-144">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="afe98-145">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="afe98-145">Exceptions</span></span>  
 <span data-ttu-id="afe98-146">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="afe98-146">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="afe98-147">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="afe98-147">Exception type</span></span>|<span data-ttu-id="afe98-148">Bedingung</span><span class="sxs-lookup"><span data-stu-id="afe98-148">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="afe98-149">– Wenn ein Steuerelement ein gefordertes Verhalten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afe98-149">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="afe98-150">– Wenn der Parameter keine gültige Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="afe98-150">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afe98-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afe98-151">See Also</span></span>  
 [<span data-ttu-id="afe98-152">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="afe98-152">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="afe98-153">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="afe98-153">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="afe98-154">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="afe98-154">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="afe98-155">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="afe98-155">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="afe98-156">Verwenden der Zwischenspeicherung in der UI-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="afe98-156">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
