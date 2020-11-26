---
title: Bewährte Methoden für Eingabehilfen
description: Erfahren Sie mehr über bewährte Methoden für die Barrierefreiheit in .net. Untersuchen Sie den programmgesteuerten Zugriff, die Benutzereinstellungen, den Entwurf der visuellen Benutzeroberfläche, die Navigation und multimodale
ms.date: 03/30/2017
helpviewer_keywords:
- best practices for accessibility
- accessibility, best practices for
ms.assetid: e6d5cd98-21a3-4b01-999c-fb953556d0e6
ms.openlocfilehash: 30961c83bdacf816856205322ac2b627d0f2594c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235687"
---
# <a name="accessibility-best-practices"></a><span data-ttu-id="31a58-104">Bewährte Methoden für die Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="31a58-104">Accessibility best practices</span></span>

> [!NOTE]
> <span data-ttu-id="31a58-105">Dieser Artikel ist für .NET Framework Entwickler gedacht, die die im-Namespace definierten Klassen der Managed UI Automation verwenden möchten <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="31a58-105">This article is intended for .NET Framework developers who want to use the managed UI Automation classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="31a58-106">Die neuesten Informationen zur Benutzeroberflächen Automatisierung finden Sie unter [Windows Automation-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="31a58-106">For the latest information about UI Automation, see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="31a58-107">Durch das Implementieren der folgenden bewährten Methoden in Steuerelementen oder Anwendungen wird die Barrierefreiheit für Personen verbessert, die Hilfstechnologiegeräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="31a58-107">Implementing the following best practices in controls or applications will improve their accessibility for people who use assistive technology devices.</span></span> <span data-ttu-id="31a58-108">Viele dieser bewährten Methoden konzentrieren sich auf einen guten Entwurf der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="31a58-108">Many of these best practices focus on good user interface (UI) design.</span></span> <span data-ttu-id="31a58-109">Jede bewährte Vorgehensweise umfasst Implementierungs Informationen für Windows Presentation Foundation (WPF)-Steuerelemente oder-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="31a58-109">Each best practice includes implementation information for Windows Presentation Foundation (WPF) controls or applications.</span></span> <span data-ttu-id="31a58-110">In vielen Fällen ist die Arbeit zum erfüllen dieser bewährten Methoden bereits in WPF-Steuerelementen enthalten.</span><span class="sxs-lookup"><span data-stu-id="31a58-110">In many cases, the work to meet these best practices is already included in WPF controls.</span></span>  
  
<a name="Programmatic_Access"></a>

## <a name="programmatic-access"></a><span data-ttu-id="31a58-111">Programmgesteuerter Zugriff</span><span class="sxs-lookup"><span data-stu-id="31a58-111">Programmatic Access</span></span>  

 <span data-ttu-id="31a58-112">Der programmgesteuerte Zugriff umfasst die Sicherstellung, dass alle Elemente der Benutzeroberfläche gekennzeichnet sind, Eigenschaftswerte verfügbar gemacht und entsprechende Ereignisse ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="31a58-112">Programmatic access involves ensuring that all UI elements are labeled, property values are exposed, and appropriate events are raised.</span></span> <span data-ttu-id="31a58-113">Für WPF-Standard Steuerelemente ist der größte Teil dieser Arbeit bereits über erfolgt <xref:System.Windows.Automation.Peers.AutomationPeer> .</span><span class="sxs-lookup"><span data-stu-id="31a58-113">For standard WPF controls, most of this work is already done through <xref:System.Windows.Automation.Peers.AutomationPeer>.</span></span> <span data-ttu-id="31a58-114">Benutzerdefinierte Steuerelemente erfordern zusätzliche Arbeit, um sicherzustellen, dass der programmgesteuerte Zugriff ordnungsgemäß implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="31a58-114">Custom controls require additional work to ensure that programmatic access is correctly implemented.</span></span>  
  
<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>

### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a><span data-ttu-id="31a58-115">Aktivieren des programmgesteuerten Zugriffs auf alle Elemente der Benutzeroberfläche und auf Text</span><span class="sxs-lookup"><span data-stu-id="31a58-115">Enable Programmatic Access to all UI Elements and Text</span></span>  

 <span data-ttu-id="31a58-116">Benutzeroberflächen Elemente (UI) sollten den programmgesteuerten Zugriff aktivieren.</span><span class="sxs-lookup"><span data-stu-id="31a58-116">User interface (UI) elements should enable programmatic access.</span></span> <span data-ttu-id="31a58-117">Wenn die Benutzeroberfläche ein Standardmäßiges WPF-Steuerelement ist, ist die Unterstützung für den programmgesteuerten Zugriff im Steuerelement enthalten.</span><span class="sxs-lookup"><span data-stu-id="31a58-117">If the UI is a standard WPF control, support for programmatic access is included in the control.</span></span> <span data-ttu-id="31a58-118">Wenn das Steuerelement ein benutzerdefiniertes Steuerelement ist, d. h. ein Steuerelement, das als Unterklasse eines allgemeinen Steuerelements oder als Unterklasse von "Control" abgeleitet wurde, müssen Sie die <xref:System.Windows.Automation.Peers.AutomationPeer> -Implementierung auf Bereiche prüfen, für die möglicherweise eine Änderung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31a58-118">If the control is a custom control – a control that has been subclassed from a common control or a control that has been subclassed from Control – then you must check the <xref:System.Windows.Automation.Peers.AutomationPeer> implementation for areas that may need modification.</span></span>  
  
 <span data-ttu-id="31a58-119">Durch Befolgen dieser bewährten Vorgehensweise können Hilfstechnologieanbieter Elemente der Benutzeroberfläche Ihres Produkts identifizieren und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="31a58-119">Following this best practice allows assistive technology vendors to identify and manipulate elements of your product's UI.</span></span>  
  
<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>

### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a><span data-ttu-id="31a58-120">Platzieren von Namen, Titeln und Beschreibungen auf Benutzeroberflächenobjekte, Frames und Seiten</span><span class="sxs-lookup"><span data-stu-id="31a58-120">Place Names, Titles, and Descriptions on UI Objects, Frames, and Pages</span></span>  

 <span data-ttu-id="31a58-121">Hilfstechnologien, insbesondere Sprachausgaben, verwenden den Titel, um die Position von Frames, Objekten oder Seiten im Navigationsschema zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="31a58-121">Assistive technologies, especially screen readers, use the title to understand the location of the frame, object, or page in the navigation scheme.</span></span> <span data-ttu-id="31a58-122">Daher muss der Titel beschreibend sein.</span><span class="sxs-lookup"><span data-stu-id="31a58-122">Therefore, the title must be descriptive.</span></span> <span data-ttu-id="31a58-123">Beispielsweise ist der Titel "Microsoft-Webseite" für eine Webseite unbrauchbar, wenn der Benutzer weit in einen bestimmten Bereich vorgedrungen ist.</span><span class="sxs-lookup"><span data-stu-id="31a58-123">For example, a Web page title of "Microsoft Web Page" is useless if the user has navigated deeply into some particular area.</span></span> <span data-ttu-id="31a58-124">Ein aussagekräftiger Titel ist wichtig für Benutzer, die blind sind und auf Sprachausgaben angewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="31a58-124">A descriptive title is critical for users who are blind and depend on screen readers.</span></span> <span data-ttu-id="31a58-125">Ebenso sind für WPF-Steuerelemente <xref:System.Windows.Automation.AutomationProperties.NameProperty> und für <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> Hilfstechnologiegeräte wichtig.</span><span class="sxs-lookup"><span data-stu-id="31a58-125">Similarly, for WPF controls, <xref:System.Windows.Automation.AutomationProperties.NameProperty> and <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> are important for assistive technology devices.</span></span>  
  
 <span data-ttu-id="31a58-126">Durch Befolgen dieser bewährten Vorgehensweise können Hilfstechnologien die Benutzeroberfläche in Beispiel Steuerelementen und-Anwendungen identifizieren und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="31a58-126">Following this best practice allows assistive technologies to identify and manipulate UI in sample controls and applications.</span></span>  
  
<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>

### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a><span data-ttu-id="31a58-127">Gewährleisten der Auslösung programmgesteuerter Ereignisse durch alle Aktivitäten auf der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="31a58-127">Ensure Programmatic Events Are Triggered by All UI Activities</span></span>  

 <span data-ttu-id="31a58-128">Durch Befolgen dieser bewährten Vorgehensweise können Hilfstechnologien auf Änderungen in der Benutzeroberfläche lauschen und den Benutzer über diese Änderungen benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="31a58-128">Following this best practice allows assistive technologies to listen for changes in the UI and notify the user about these changes.</span></span>  
  
<a name="User_Settings"></a>

## <a name="user-settings"></a><span data-ttu-id="31a58-129">Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="31a58-129">User Settings</span></span>  

 <span data-ttu-id="31a58-130">Die bewährte Methode in diesem Abschnitt stellt sicher, dass Steuerelemente oder Anwendungen die Benutzereinstellungen nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="31a58-130">The best practice in this section ensures that controls or applications do not override user settings.</span></span>  
  
<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>

### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a><span data-ttu-id="31a58-131">Respektieren aller systemweiten Einstellungen und Beachten der Barrierefreiheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="31a58-131">Respect All System-Wide Settings and Do Not Interfere with Accessibility Functions</span></span>  

 <span data-ttu-id="31a58-132">Benutzer können einige systemweite Flags über die Systemsteuerung festlegen, während andere Flags programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="31a58-132">Users can use the Control Panel to set some system-wide flags; other flags can be set programmatically.</span></span> <span data-ttu-id="31a58-133">Diese Einstellungen dürfen nicht von Steuerelementen oder Anwendungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="31a58-133">These settings should not be changed by controls or applications.</span></span> <span data-ttu-id="31a58-134">Darüber hinaus müssen Anwendungen die Einstellungen für die Barrierefreiheit ihres Hostbetriebssystems unterstützen.</span><span class="sxs-lookup"><span data-stu-id="31a58-134">Also, applications must support the accessibility settings of their host operating system.</span></span>  
  
 <span data-ttu-id="31a58-135">Durch Befolgen dieser bewährten Methode können Benutzer Einstellungen für die Barrierefreiheit festlegen und dadurch wissen, dass diese Einstellungen von Anwendungen nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="31a58-135">Following this best practice allows users to set accessibility settings and know that those settings will not be changed by applications.</span></span>  
  
<a name="Visual_UI_Design"></a>

## <a name="visual-ui-design"></a><span data-ttu-id="31a58-136">Entwurf der visuellen Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="31a58-136">Visual UI Design</span></span>  

 <span data-ttu-id="31a58-137">Die bewährten Methoden in diesem Abschnitt stellen sicher, dass Steuerelemente oder Anwendungen Farben und Bilder effektiv verwenden und von Hilfstechnologien verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="31a58-137">Best Practices in this section ensure that controls or applications use color and images effectively and are able to be used by Assistive technologies.</span></span>  
  
<a name="Don_t_Hard_Code_Colors"></a>

### <a name="dont-hard-code-colors"></a><span data-ttu-id="31a58-138">Vermeiden hartcodierter Farben</span><span class="sxs-lookup"><span data-stu-id="31a58-138">Don't Hard-Code Colors</span></span>  

 <span data-ttu-id="31a58-139">Personen, die farbenblind sind, eine Sehschwäche aufweisen oder einen monochromen Bildschirm verwenden, können Anwendungen mit hartcodierten Farben möglicherweise nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="31a58-139">People who are color blind, have low vision, or are using a black and white screen might not be able to use applications with hard-coded colors.</span></span>  
  
 <span data-ttu-id="31a58-140">Durch Befolgen dieser bewährten Methode können Benutzer die Farbkombinationen auf Grundlage individueller Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="31a58-140">Following this best practice allows users to adjust color combinations based on individual needs.</span></span>  
  
<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>

### <a name="support-high-contrast-and-all-system-display-attributes"></a><span data-ttu-id="31a58-141">Unterstützen von hohem Kontrast und allen Systemanzeigeattributen</span><span class="sxs-lookup"><span data-stu-id="31a58-141">Support High Contrast and all System Display Attributes</span></span>  

 <span data-ttu-id="31a58-142">Anwendungen sollten vom Benutzer ausgewählte, systemweite Kontrasteinstellungen, Farbauswahlen oder andere systemweite Anzeigeeinstellungen und -attribute nicht stören oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="31a58-142">Applications should not disrupt or disable user-selected, system-wide contrast settings, color selections, or other system-wide display settings and attributes.</span></span> <span data-ttu-id="31a58-143">Die von einem Benutzer übernommenen systemweiten Einstellungen erhöhen die Barrierefreiheit von Anwendungen, daher sollten sie von Anwendungen nicht deaktiviert oder ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="31a58-143">System-wide settings adopted by a user enhance the accessibility of applications, so they should not be disabled or disregarded by applications.</span></span> <span data-ttu-id="31a58-144">Farben müssen in der richtigen Kombination für Vorder- und Hintergrund verwendet werden, um den geeigneten Kontrast zu bieten.</span><span class="sxs-lookup"><span data-stu-id="31a58-144">Color should be used in their correct foreground-on-background combination to provide proper contrast.</span></span> <span data-ttu-id="31a58-145">Kombinieren Sie keine nicht verknüpften Farben, und ändern Sie keine Farben.</span><span class="sxs-lookup"><span data-stu-id="31a58-145">Don't mix unrelated colors, and don't reverse colors.</span></span>  
  
 <span data-ttu-id="31a58-146">Viele Benutzer benötigen bestimmte kontrastreiche Kombinationen, z. B. weißen Text auf schwarzem Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="31a58-146">Many users require specific high-contrast combinations, such as white text on a black background.</span></span> <span data-ttu-id="31a58-147">Die invertierte Darstellung mit schwarzem Text auf weißem Hintergrund führt dazu, dass der Hintergrund auf den Vordergrund übergreift und das Lesen für manche Benutzer erschwert wird.</span><span class="sxs-lookup"><span data-stu-id="31a58-147">Drawing these reversed, as black text on a white background causes the background to bleed over the foreground and can make reading difficult for some users.</span></span>  
  
<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>

### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a><span data-ttu-id="31a58-148">Gewährleisten der ordnungsgemäßen Skalierung aller Benutzeroberflächenelemente bei beliebiger DPI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="31a58-148">Ensure All UI Correctly Scales by Any DPI Setting</span></span>  

 <span data-ttu-id="31a58-149">Stellen Sie sicher, dass die gesamte Benutzeroberfläche nach jeder dpi-Einstellung (dpi) ordnungsgemäß skaliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="31a58-149">Ensure that all UI can correctly scale by any dots per inch (dpi) setting.</span></span> <span data-ttu-id="31a58-150">Stellen Sie außerdem sicher, dass Benutzeroberflächen Elemente in einem Bildschirm von 1024 x 768 mit 120 Punkten pro Zoll (dpi) passen.</span><span class="sxs-lookup"><span data-stu-id="31a58-150">Also, ensure that UI elements fit in a screen of 1024 x 768 with 120 dots per inch (dpi).</span></span>  
  
<a name="Navigation"></a>

## <a name="navigation"></a><span data-ttu-id="31a58-151">Navigation</span><span class="sxs-lookup"><span data-stu-id="31a58-151">Navigation</span></span>  

 <span data-ttu-id="31a58-152">Die bewährten Methoden in diesem Abschnitt stellen sicher, dass die Navigation auf Steuerelemente und Anwendungen ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="31a58-152">Best Practices in this section ensure that navigation has been addressed for controls and applications.</span></span>  
  
<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>

### <a name="provide-keyboard-interface-for-all-ui-elements"></a><span data-ttu-id="31a58-153">Bereitstellen einer Tastaturschnittstelle für alle Elemente der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="31a58-153">Provide Keyboard Interface for All UI Elements</span></span>  

 <span data-ttu-id="31a58-154">Tabstopps, insbesondere wenn Sie sorgfältig geplant sind, haben Benutzern eine weitere Möglichkeit, die Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="31a58-154">Tab stops, especially when carefully planned, give users another way to navigate the UI.</span></span>  
  
 <span data-ttu-id="31a58-155">Anwendungen sollten die folgenden Tastaturschnittstellen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="31a58-155">Applications should provide the following keyboard interfaces:</span></span>  
  
- <span data-ttu-id="31a58-156">Tabstopps für alle Steuerelemente, mit denen der Benutzer interagieren kann, z. B. Schaltflächen, Links oder Listenfelder</span><span class="sxs-lookup"><span data-stu-id="31a58-156">tab stops for all controls that the user can interact with, such as buttons, links, or list boxes</span></span>  
  
- <span data-ttu-id="31a58-157">Logische Aktivierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="31a58-157">logical tab order</span></span>  
  
<a name="Show_the_Keyboard_Focus"></a>

### <a name="show-the-keyboard-focus"></a><span data-ttu-id="31a58-158">Anzeigen des Tastaturfokus</span><span class="sxs-lookup"><span data-stu-id="31a58-158">Show the Keyboard Focus</span></span>  

 <span data-ttu-id="31a58-159">Benutzer müssen wissen, welches Objekt den Tastaturfokus hat, damit sie die Auswirkungen ihrer Tastatureingaben voraussehen können.</span><span class="sxs-lookup"><span data-stu-id="31a58-159">Users need to know which object has the keyboard focus so that they can anticipate the effect of their keystrokes.</span></span> <span data-ttu-id="31a58-160">Verwenden Sie Farben, Schriftarten oder grafische Darstellungen (z. B. Rechtecke oder eine Vergrößerung), um den Tastaturfokus hervorzuheben.</span><span class="sxs-lookup"><span data-stu-id="31a58-160">To highlight the keyboard focus, use colors, fonts, or graphics such as rectangles or magnification.</span></span> <span data-ttu-id="31a58-161">Um den Tastaturfokus zu verdeutlichen, ändern Sie das Volume, die Größe oder die Tonqualität.</span><span class="sxs-lookup"><span data-stu-id="31a58-161">To audibly highlight the keyboard focus, change the volume, pitch, or tonal quality.</span></span>  
  
 <span data-ttu-id="31a58-162">Um Verwechselungen zu vermeiden, sollten Anwendungen alle visuellen Fokusindikatoren ausblenden und die Auswahl abblenden, die sich in inaktiven Fenstern (oder Bereichen) befindet.</span><span class="sxs-lookup"><span data-stu-id="31a58-162">To avoid confusion, applications should hide all visual focus indicators and dim selections that are located in inactive windows (or panes).</span></span>  
  
 <span data-ttu-id="31a58-163">Anwendungen sollten beim Tastaturfokus wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="31a58-163">Applications should do the following with keyboard focus:</span></span>  
  
- <span data-ttu-id="31a58-164">Der Tastaturfokus sollte immer bei einem Element liegen.</span><span class="sxs-lookup"><span data-stu-id="31a58-164">one item should always have keyboard focus</span></span>  
  
- <span data-ttu-id="31a58-165">Der Tastaturfokus muss sichtbar und unverkennbar sein.</span><span class="sxs-lookup"><span data-stu-id="31a58-165">keyboard focus should be visible and obvious</span></span>  
  
- <span data-ttu-id="31a58-166">Die Auswahl und/oder Elemente mit Fokus müssen visuell hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="31a58-166">selections and/or focused items should be visually highlighted</span></span>  
  
<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>

### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a><span data-ttu-id="31a58-167">Unterstützen von Navigationsstandards und leistungsstarken Navigationsschemas</span><span class="sxs-lookup"><span data-stu-id="31a58-167">Support Navigation Standards and Powerful Navigation Schemes</span></span>  

 <span data-ttu-id="31a58-168">Verschiedene Aspekte der Tastaturnavigation bieten verschiedene Möglichkeiten für Benutzer, die Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="31a58-168">Different aspects of keyboard navigation provide different ways for users to navigate the UI.</span></span>  
  
 <span data-ttu-id="31a58-169">Anwendungen sollten die folgenden Tastaturschnittstellen bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="31a58-169">Applications should provide the following keyboard interfaces:</span></span>  
  
- <span data-ttu-id="31a58-170">Tastenkombinationen und unterstrichene Zugriffstasten für alle Befehle, Menüs und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="31a58-170">shortcut keys and underlined access keys for all commands, menus, and controls</span></span>  
  
- <span data-ttu-id="31a58-171">Tastenkombinationen für wichtige Links</span><span class="sxs-lookup"><span data-stu-id="31a58-171">keyboard shortcuts to important links</span></span>  
  
- <span data-ttu-id="31a58-172">Alle Menüelemente verfügen über eine Tastenkombination, alle Schaltflächen verfügen über Tastenkombinationen, alle Befehle verfügen über eine Tastenkombination.</span><span class="sxs-lookup"><span data-stu-id="31a58-172">all menu items have an access key; all buttons have accelerator keys, all commands have an accelerator key.</span></span>  
  
<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>

### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a><span data-ttu-id="31a58-173">Vermeiden störender Auswirkungen der Mausposition auf die Tastaturnavigation</span><span class="sxs-lookup"><span data-stu-id="31a58-173">Do Not Let Mouse Location Interfere with Keyboard Navigation</span></span>  

 <span data-ttu-id="31a58-174">Die Position des Mauszeigers sollte nicht die Tastaturnavigation behindern.</span><span class="sxs-lookup"><span data-stu-id="31a58-174">Mouse location should not interfere with keyboard navigation.</span></span> <span data-ttu-id="31a58-175">Wenn sich die Maus z. b. an einer bestimmten Position befindet und der Benutzer mit der Tastatur navigiert, darf ein Mausklick nur auftreten, wenn er vom Benutzer initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="31a58-175">For example, if the mouse is positioned some place and the user is navigating with the keyboard, a mouse click should not happen unless initiated by the user.</span></span>  
  
<a name="Multimodal_Interface"></a>

## <a name="multimodal-interface"></a><span data-ttu-id="31a58-176">Multimodale Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31a58-176">Multimodal Interface</span></span>  

 <span data-ttu-id="31a58-177">Die bewährten Methoden in diesem Abschnitt stellen sicher, dass die Benutzeroberfläche der Anwendung Alternativen für visuelle Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="31a58-177">Best Practices in this section ensure that application UI includes alternatives for visual elements.</span></span>  
  
<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>

### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a><span data-ttu-id="31a58-178">Bereitstellen von auswählbaren Entsprechungen für Nicht-Text-Elemente</span><span class="sxs-lookup"><span data-stu-id="31a58-178">Provide User-Selectable Equivalents for Non-Text Elements</span></span>  

 <span data-ttu-id="31a58-179">Geben Sie für jedes Nicht-Textelement eine vom Benutzer auswählbare Entsprechung für Text, Aufzeichnungen oder Audiobeschreibungen ein, z. B. alternativen Text, Beschriftungen oder visuelles Feedback.</span><span class="sxs-lookup"><span data-stu-id="31a58-179">For each non-text element, provide a user-selectable equivalent for text, transcripts, or audio descriptions, such as alt text, captions, or visual feedback.</span></span>  
  
 <span data-ttu-id="31a58-180">Nicht-Textelemente decken eine breite Palette von Elementen der Benutzeroberfläche ab, einschließlich: Bilder, Imagemapbereiche, Animationen, Applets, Frames, Skripts, grafische Schaltflächen, Sounds, eigenständige Audiodateien und Videos.</span><span class="sxs-lookup"><span data-stu-id="31a58-180">Non-text elements cover a wide range of UI elements including: images, image map regions, animations, applets, frames, scripts, graphical buttons, sounds, stand-alone audio files, and video.</span></span> <span data-ttu-id="31a58-181">Nicht-Textelemente sind wichtig, wenn Sie visuelle Informationen, Sprache oder allgemeine Audioinformationen enthalten, auf die der Benutzer Zugriff hat, um den Inhalt der Benutzeroberfläche zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="31a58-181">Non-text elements are important when they contain visual information, speech, or general audio information that the user needs access to in order to understand the content of the UI.</span></span>  
  
<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>

### <a name="use-color-but-also-provide-alternatives-to-color"></a><span data-ttu-id="31a58-182">Verwenden von Farbe und Bereitstellen von Alternativen für Farbe</span><span class="sxs-lookup"><span data-stu-id="31a58-182">Use Color but Also Provide Alternatives to Color</span></span>  

 <span data-ttu-id="31a58-183">Verwenden Sie Farbe, um Informationen aufzuwerten, zu betonen oder auf andere Weise angezeigte Informationen zu wiederholen. Vermitteln Sie die Informationen jedoch nicht ausschließlich über die Farbe.</span><span class="sxs-lookup"><span data-stu-id="31a58-183">Use color to enhance, emphasize, or reiterate information shown by other means, but do not communicate information by using color alone.</span></span> <span data-ttu-id="31a58-184">Benutzer, die farbenblind sind oder ein monochromes Display verwenden, benötigen Alternativen zu Farben.</span><span class="sxs-lookup"><span data-stu-id="31a58-184">Users who are color blind or have a monochrome display need alternatives to color.</span></span>  
  
<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>

### <a name="use-standard-input-apis-with-device-independent-calls"></a><span data-ttu-id="31a58-185">Verwenden von Standardeingabe-APIs mit geräteunabhängigen Aufrufen</span><span class="sxs-lookup"><span data-stu-id="31a58-185">Use Standard Input APIs with Device-Independent Calls</span></span>  

 <span data-ttu-id="31a58-186">Geräteunabhängige Aufrufe stellen die Gleichheit von Tastatur-und Mausfunktionen sicher, während Sie Hilfstechnologien mit erforderlichen Informationen über die Benutzeroberfläche bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="31a58-186">Device-independent calls ensure keyboard and mouse feature equality, while providing assistive technology with needed information about the UI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a58-187">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31a58-187">See also</span></span>

- <xref:System.Windows.Automation.Peers>
- <span data-ttu-id="31a58-188">[NumericUpDown Custom Control with Theme and UI Automation Support Sample(Benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung)](/previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="31a58-188">[NumericUpDown Custom Control with Theme and UI Automation Support Sample](/previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90))</span></span>
- [<span data-ttu-id="31a58-189">Richtlinien zur Gestaltung einer tastaturgesteuerten Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="31a58-189">Guidelines for Keyboard User Interface Design</span></span>](/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design)
