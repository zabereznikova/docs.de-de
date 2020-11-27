---
title: Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Überprüfen Sie die Richtlinien und Konventionen, um das Fenster Steuerelement Muster in der Benutzeroberflächen Automatisierung Sie müssen erforderliche Member für die IWindowProvider-Schnittstelle kennen.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: b43884393974e6f2863da6a4a5ca8f305e5a160c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286096"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="bcaac-104">Implementieren des Window-Steuerelementmusters der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="bcaac-104">Implementing the UI Automation Window Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="bcaac-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="bcaac-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bcaac-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="bcaac-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="bcaac-107">Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IWindowProvider>, einschließlich Informationen über <xref:System.Windows.Automation.WindowPattern> -Eigenschaften, -Methoden und -Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="bcaac-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="bcaac-108">Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="bcaac-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="bcaac-109">Das- <xref:System.Windows.Automation.WindowPattern> Steuerelement Muster wird zur Unterstützung von Steuerelementen verwendet, die grundlegende fensterbasierte Funktionen in einer herkömmlichen grafischen Benutzeroberfläche (GUI) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bcaac-109">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional graphical user interface (GUI).</span></span> <span data-ttu-id="bcaac-110">Beispiele für Steuerelemente, die dieses Steuerelement Muster implementieren müssen, sind u. a. Anwendungsfenster der obersten Ebene, untergeordnete MDI-Fenster (Multiple Document Interface), in der Größe umsetzbare Steuerelemente für geteilte Bereiche, Modale Dialoge und</span><span class="sxs-lookup"><span data-stu-id="bcaac-110">Examples of controls that must implement this control pattern include top-level application windows, multiple-document interface (MDI) child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="bcaac-111">Implementierungsrichtlinien und -konventionen</span><span class="sxs-lookup"><span data-stu-id="bcaac-111">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="bcaac-112">Beachten Sie beim Implementieren des Window-Steuerelementmusters die folgenden Richtlinien und Konventionen:</span><span class="sxs-lookup"><span data-stu-id="bcaac-112">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="bcaac-113">Damit ein Steuerelement in der Lage ist, Fenstergröße und Bildschirmposition über Benutzeroberflächenautomatisierung zu ändern, muss es <xref:System.Windows.Automation.Provider.ITransformProvider> zusätzlich zu <xref:System.Windows.Automation.Provider.IWindowProvider>implementieren.</span><span class="sxs-lookup"><span data-stu-id="bcaac-113">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="bcaac-114">Für Steuerelemente, die Titelleisten und Titelleistenelemente enthalten, mit denen das Steuerelement verschoben, maximiert, minimiert, geschlossen oder in der Größe verändert werden kann, muss üblicherweise <xref:System.Windows.Automation.Provider.IWindowProvider>implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="bcaac-114">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="bcaac-115">Für Steuerelemente wie QuickInfo-Popups und Dropdown-Kombinationsfelder oder -Menüs muss <xref:System.Windows.Automation.Provider.IWindowProvider>normalerweise nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="bcaac-115">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
- <span data-ttu-id="bcaac-116">Hilfefenster in Sprechblasenform unterscheiden sich von normalen QuickInfo-Popups darin, dass sie eine wie für Fenster verwendete Schaltfläche zum Schließen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bcaac-116">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
- <span data-ttu-id="bcaac-117">Der Vollbildmodus wird von IWindowProvider nicht unterstützt, da er featurespezifisch für eine Anwendung und kein typisches Fensterverhalten ist.</span><span class="sxs-lookup"><span data-stu-id="bcaac-117">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>

## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="bcaac-118">Erforderliche Member für IWindowProvider</span><span class="sxs-lookup"><span data-stu-id="bcaac-118">Required Members for IWindowProvider</span></span>  

 <span data-ttu-id="bcaac-119">Die folgenden Eigenschaften, Methoden und Ereignisse sind für die IWindowProvider-Schnittstelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bcaac-119">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="bcaac-120">Erforderlicher Member</span><span class="sxs-lookup"><span data-stu-id="bcaac-120">Required member</span></span>|<span data-ttu-id="bcaac-121">Memberart</span><span class="sxs-lookup"><span data-stu-id="bcaac-121">Member type</span></span>|<span data-ttu-id="bcaac-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bcaac-122">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="bcaac-123">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcaac-123">Property</span></span>|<span data-ttu-id="bcaac-124">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="bcaac-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcaac-125">Property</span></span>|<span data-ttu-id="bcaac-126">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="bcaac-127">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcaac-127">Property</span></span>|<span data-ttu-id="bcaac-128">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="bcaac-129">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcaac-129">Property</span></span>|<span data-ttu-id="bcaac-130">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="bcaac-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcaac-131">Property</span></span>|<span data-ttu-id="bcaac-132">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="bcaac-133">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcaac-133">Property</span></span>|<span data-ttu-id="bcaac-134">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="bcaac-135">Methode</span><span class="sxs-lookup"><span data-stu-id="bcaac-135">Method</span></span>|<span data-ttu-id="bcaac-136">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="bcaac-137">Methode</span><span class="sxs-lookup"><span data-stu-id="bcaac-137">Method</span></span>|<span data-ttu-id="bcaac-138">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-138">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="bcaac-139">Methode</span><span class="sxs-lookup"><span data-stu-id="bcaac-139">Method</span></span>|<span data-ttu-id="bcaac-140">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="bcaac-141">Ereignis</span><span class="sxs-lookup"><span data-stu-id="bcaac-141">Event</span></span>|<span data-ttu-id="bcaac-142">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="bcaac-143">Ereignis</span><span class="sxs-lookup"><span data-stu-id="bcaac-143">Event</span></span>|<span data-ttu-id="bcaac-144">Keine</span><span class="sxs-lookup"><span data-stu-id="bcaac-144">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="bcaac-145">Ereignis</span><span class="sxs-lookup"><span data-stu-id="bcaac-145">Event</span></span>|<span data-ttu-id="bcaac-146"><xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="bcaac-146">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="bcaac-147">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="bcaac-147">Exceptions</span></span>  

 <span data-ttu-id="bcaac-148">Anbieter müssen die folgenden Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="bcaac-148">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="bcaac-149">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="bcaac-149">Exception type</span></span>|<span data-ttu-id="bcaac-150">Bedingung</span><span class="sxs-lookup"><span data-stu-id="bcaac-150">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="bcaac-151">: Wenn ein Steuerelement ein angefordertes Verhalten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bcaac-151">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="bcaac-152">-Wenn der-Parameter keine gültige Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="bcaac-152">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcaac-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bcaac-153">See also</span></span>

- [<span data-ttu-id="bcaac-154">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="bcaac-154">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="bcaac-155">Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="bcaac-155">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="bcaac-156">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="bcaac-156">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="bcaac-157">Übersicht über die Benutzeroberflächenautomatisierungs-Struktur</span><span class="sxs-lookup"><span data-stu-id="bcaac-157">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="bcaac-158">Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="bcaac-158">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
