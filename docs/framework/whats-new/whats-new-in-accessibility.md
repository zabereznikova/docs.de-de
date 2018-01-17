---
title: Neuerungen der Barrierefreiheit in .NET Framework
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="df703-102">Neuerungen der Barrierefreiheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="df703-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="df703-103">Die Anwendungen von .NET Framework sollen eine bessere Barrierefreiheit für Ihre Benutzer bieten.</span><span class="sxs-lookup"><span data-stu-id="df703-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="df703-104">Durch Barrierefreiheitsfunktionen wird es einer Anwendung ermöglicht, den Benutzern von Hilfstechnologien ein angemessenes Erlebnis zu bieten.</span><span class="sxs-lookup"><span data-stu-id="df703-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="df703-105">Ab .NET Framework 4.7.1 enthält .NET Framework zahlreiche Verbesserungen der Barrierefreiheit, die es den Entwicklern ermöglichen, barrierefreie Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df703-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="df703-106">Die neuen Barrierefreiheitsfunktionen werden standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen.</span><span class="sxs-lookup"><span data-stu-id="df703-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="df703-107">Zusätzlich können Anwendungen, die eine frühere Version von .NET Framework anzielen, aber unter .NET Framework 4.7.1 oder höher ausgeführt werden, veraltete Verhaltensweisen für die Barrierefreiheit deaktivieren (und dadurch die Verbesserungen der Barrierefreiheit in .NET Framework 4.7.1 aktivieren), indem folgendes Element zum [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="df703-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="df703-108">Auf ähnliche Weise können Anwendungen, die Versionen von .NET Framework ab 4.7.1 anzielen, die Barrierefreiheitsfunktionen deaktivieren, indem folgendes Element zum [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="df703-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="df703-109">Neuerungen der Barrierefreiheit in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="df703-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="df703-110">.NET Framework 4.7.1 enthält neue Barrierefreiheitsfunktionen für folgende Bereiche:</span><span class="sxs-lookup"><span data-stu-id="df703-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="df703-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="df703-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="df703-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df703-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="df703-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="df703-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="df703-114">**Verbesserungen der Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="df703-114">**Screen reader improvements**</span></span>

<span data-ttu-id="df703-115">Wenn die Verbesserungen der Barrierefreiheit aktiviert sind, enthält .NET Framework 4.7.1 folgende Verbesserungen, die sich auf die Sprachausgabe auswirken:</span><span class="sxs-lookup"><span data-stu-id="df703-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="df703-116">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.Expander>-Steuerelemente von der Sprachausgabe als Schaltflächen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="df703-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="df703-117">Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als erweiterbare bzw. reduzierbare Gruppen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="df703-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="df703-118">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.DataGridCell>-Steuerelemente von der Sprachausgabe als „benutzerdefiniert“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="df703-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="df703-119">Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als (lokalisierte) Datenrasterzellen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="df703-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="df703-120">Ab .NET Framework 4.7.1 gibt die Sprachausgabe den Namen einer bearbeitbaren <xref:System.Windows.Controls.ComboBox>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="df703-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="df703-121">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.PasswordBox>-Steuerelemente als „Es befindet sich kein Element in der Ansicht.“ ausgegeben oder wiesen andere fehlerhafte Verhaltensweisen auf.</span><span class="sxs-lookup"><span data-stu-id="df703-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="df703-122">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="df703-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="df703-123">**Unterstützung von dynamischen Bereichen für die UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="df703-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="df703-124">Die Sprachausgabe unterstützt die Benutzer beim Lesen der Inhalte der Benutzeroberfläche einer Anwendung. Dies geschieht üblicherweise durch eine Sprachausgabe des Texts der Inhalte der Benutzeroberfläche, die den Fokus besitzen.</span><span class="sxs-lookup"><span data-stu-id="df703-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="df703-125">Wenn ein Element der Benutzeroberfläche sich jedoch verändert oder den Fokus nicht besitzt, wird der Benutzer möglicherweise nicht benachrichtigt, wodurch ihm wichtige Informationen entgehen können.</span><span class="sxs-lookup"><span data-stu-id="df703-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="df703-126">Durch dynamische Bereiche soll dieses Problem behoben werden.</span><span class="sxs-lookup"><span data-stu-id="df703-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="df703-127">Entwickler können diese verwenden, um der Sprachausgabe oder einem anderen UIAutomation-Client mitzuteilen, dass eine wichtige Änderung an einem Element der Benutzeroberfläche vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="df703-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="df703-128">Die Sprachausgabe kann dann entscheiden, wie und wann der Benutzer über diese Änderung informiert wird.</span><span class="sxs-lookup"><span data-stu-id="df703-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="df703-129">Folgende APIs wurden zu WPF hinzugefügt, um dynamische Bereiche zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="df703-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="df703-130">Die <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>-Felder, die die **LiveSetting**-Eigenschaft und das **LiveRegionChanged**-Ereignis identifizieren.</span><span class="sxs-lookup"><span data-stu-id="df703-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="df703-131">Diese können mithilfe von XAML festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="df703-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="df703-132">Die angefügte Eigenschaft **AutomationProperties.LiveSetting**, die der Sprachausgabe die Wichtigkeit der Änderung der Benutzeroberfläche für den Benutzer mitteilt.</span><span class="sxs-lookup"><span data-stu-id="df703-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="df703-133">Die <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>-Eigenschaft, die die angefügte Eigenschaft **AutomationProperties.LiveSetting** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="df703-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="df703-134">Die <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>-Methode, die überschrieben werden kann, um einen **LiveSetting**-Wert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="df703-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="df703-135">Die <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>-Methoden, die einen **LiveSetting**-Wert abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="df703-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="df703-136">Die <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>-Enumeration, die die folgenden möglichen **LiveSetting**-Werte definiert:</span><span class="sxs-lookup"><span data-stu-id="df703-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="df703-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="df703-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="df703-138">Das Element sendet keine Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="df703-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="df703-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="df703-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="df703-140">Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="df703-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="df703-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="df703-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="df703-142">Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="df703-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="df703-143">Sie können einen dynamischen Bereich erstellen, indem Sie die Eigenschaft **AutomationProperties.LiveSetting** wie im folgenden Beispiel dargestellt auf das relevante Element festlegen:</span><span class="sxs-lookup"><span data-stu-id="df703-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="df703-144">Wenn die Daten im dynamischen Bereich geändert werden und diese Änderung der Sprachausgabe mitgeteilt werden soll, müssen Sie wie im folgenden Beispiel dargestellt explizit ein Ereignis auslösen.</span><span class="sxs-lookup"><span data-stu-id="df703-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="df703-145">**Hoher Kontrast**</span><span class="sxs-lookup"><span data-stu-id="df703-145">**High contrast**</span></span>

<span data-ttu-id="df703-146">Ab .NET Framework 4.7.1 wurden Verbesserungen am Design „Hoher Kontrast“ für verschiedene WPF-Steuerelemente vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="df703-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="df703-147">Diese sind nun sichtbar, wenn das <xref:System.Windows.SystemParameters.HighContrast%2A>-Design festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="df703-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="df703-148">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="df703-148">These include:</span></span>

- <span data-ttu-id="df703-149"><xref:System.Windows.Controls.Expander>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="df703-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="df703-150">Das visuelle Fokuselement für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df703-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="df703-151">Das visuelle Tastaturelement für die <xref:System.Windows.Controls.ComboBox>-, <xref:System.Windows.Controls.ListBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df703-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="df703-152">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df703-152">For example:</span></span>

    <span data-ttu-id="df703-153">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-153">Before:</span></span> 
    
    ![Das Expander-Steuerelement mit Fokus vor der Verbesserung der Barrierefreiheit](media/expander-before.png)

    <span data-ttu-id="df703-155">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-155">After:</span></span> 

    ![Das Expander-Steuerelement mit Fokus nach der Verbesserung der Barrierefreiheit](media/expander-after.png)

- <span data-ttu-id="df703-157"><xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="df703-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="df703-158">Der Text in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen ist nun leichter zu erkennen, wenn das Design mit hohem Kontrast ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="df703-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="df703-159">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df703-159">For example:</span></span>

    <span data-ttu-id="df703-160">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-160">Before:</span></span> 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus vor der Verbesserung der Barrierefreiheit](media/radio-button-before.png)
    
    <span data-ttu-id="df703-162">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-162">After:</span></span> 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus nach der Verbesserung der Barrierefreiheit](media/radio-button-after.png)

- <span data-ttu-id="df703-164"><xref:System.Windows.Controls.ComboBox>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="df703-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="df703-165">Ab .NET Framework 4.7.1 hat der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Steuerelements die gleiche Farbe wie der deaktivierte Text.</span><span class="sxs-lookup"><span data-stu-id="df703-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="df703-166">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df703-166">For example:</span></span>
    
    <span data-ttu-id="df703-167">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-167">Before:</span></span> 

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements vor der Verbesserung der Barrierefreiheit](media/combo-disabled-before.png)

    <span data-ttu-id="df703-169">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-169">After:</span></span>   

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements nach der Verbesserung der Barrierefreiheit](media/combo-disabled-after.png)

    <span data-ttu-id="df703-171">Darüber hinaus verwenden deaktivierte Schaltflächen und Schaltflächen mit Fokus das richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="df703-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="df703-172">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-172">Before:</span></span>

    ![Farbdesign der Schaltflächen vor der Verbesserung der Barrierefreiheit](media/button-themes-before.png) 
    
    <span data-ttu-id="df703-174">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-174">After:</span></span> 

    ![Farbdesign der Schaltflächen nach der Verbesserung der Barrierefreiheit](media/button-themes-after.png) 

    <span data-ttu-id="df703-176">In .NET Framework 4.7 und früher führte das Festlegen des Formats eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf `Toolbar.ComboBoxStyleKey` dazu, dass der Dropdownpfeil nicht angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="df703-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="df703-177">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="df703-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="df703-178">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df703-178">For example:</span></span>

    <span data-ttu-id="df703-179">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-179">Before:</span></span> 

    ![„Toolbar.ComboBoxStyleKey“ vor der Verbesserung der Barrierefreiheit](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="df703-181">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-181">After:</span></span> 

    ![„Toolbar.ComboBoxStyleKey“ nach der Verbesserung der Barrierefreiheit](media/comboboxstylekey-after.png) 

- <span data-ttu-id="df703-183"><xref:System.Windows.Controls.DataGrid>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="df703-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="df703-184">Ab .NET Framework 4.7.1 verwendet der Pfeil für die Sortieranzeige in den <xref:System.Windows.Controls.DataGrid>-Steuerelementen das richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="df703-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="df703-185">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df703-185">For example:</span></span>

    <span data-ttu-id="df703-186">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-186">Before:</span></span> 

    ![Pfeil für die Sortieranzeige vor der Verbesserung der Barrierefreiheit](media/sort-indicator-before.png) 
    
    <span data-ttu-id="df703-188">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-188">After:</span></span>   
 
    ![Pfeil für die Sortieranzeige nach der Verbesserung der Barrierefreiheit](media/sort-indicator-after.png) 
    
    <span data-ttu-id="df703-190">Darüber hinaus wurde in .NET Framework 4.7 und früher das Standarddesign für Links geändert, wodurch Links beim Bewegen der Maus über diese im Modus mit hohem Kontrast in der falschen Farbe angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="df703-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="df703-191">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="df703-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="df703-192">Auf ähnliche Weise verwenden die Spalten des Kontrollkästchens <xref:System.Windows.Controls.DataGrid> ab .NET Framework 4.7.1 die erwarteten Farben für das Feedback des Tastaturfokus.</span><span class="sxs-lookup"><span data-stu-id="df703-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="df703-193">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-193">Before:</span></span> 

    ![DataGrid-Standarddesign für Links vor der Verbesserung der Barrierefreiheit](media/default-link-style-before.png) 
 
    <span data-ttu-id="df703-195">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-195">After:</span></span>    
  
    ![DataGrid-Standarddesign für Links nach der Verbesserung der Barrierefreiheit](media/default-link-style-after.png)  

<span data-ttu-id="df703-197">Weitere Informationen zu Verbesserungen der WPF-Barrierefreiheit in .NET Framework 4.7.1 finden Sie unter [Verbesserung der Barrierefreiheit in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="df703-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="df703-198">Verbesserung der Barrierefreiheit von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="df703-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="df703-199">In .NET Framework 4.7.1 enthält Windows Forms (WinForms) Verbesserungen der Barrierefreiheit für folgende Bereiche:</span><span class="sxs-lookup"><span data-stu-id="df703-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="df703-200">**Verbesserte Anzeige im Modus mit hohem Kontrast**</span><span class="sxs-lookup"><span data-stu-id="df703-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="df703-201">Ab .NET Framework 4.7.1 bieten viele WinForms-Steuerelemente ein verbessertes Rendering für die Modi mit hohem Kontrast, die im Betriebssystem verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="df703-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="df703-202">In Windows 10 wurden die Werte für einige Systemfarbe im Design mit hohem Kontrast geändert, und Windows Forms basiert auf dem Win32-Framework von Windows 10.</span><span class="sxs-lookup"><span data-stu-id="df703-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="df703-203">Führen Sie für die besten Ergebnisse die aktuelle Version von Windows aus, und aktivieren Sie die neuesten Änderungen am Betriebssystem, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus der supportedOS-Zeile für Windows 10 entfernen, sodass diese folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="df703-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="df703-204">Folgende Änderungen wurden am Design mit hohem Kontrast vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="df703-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="df703-205">Die Kontrollkästchen der <xref:System.Windows.Forms.MenuStrip>-Elemente können einfacher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="df703-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="df703-206">Wenn diese aktiviert werden, können deaktivierte <xref:System.Windows.Forms.MenuStrip>-Elemente einfacher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="df703-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="df703-207">Der Text in einem ausgewählten <xref:System.Windows.Forms.Button>-Kontrollkästchen bildet einen Kontrast zur Auswahlfarbe.</span><span class="sxs-lookup"><span data-stu-id="df703-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="df703-208">Deaktivierter Text ist einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="df703-208">Disabled text is easier to read.</span></span> <span data-ttu-id="df703-209">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df703-209">For example:</span></span>

    <span data-ttu-id="df703-210">Vorher:</span><span class="sxs-lookup"><span data-stu-id="df703-210">Before:</span></span>

    ![Deaktivierter Text vor der Verbesserung der Barrierefreiheit](media/wf-disabled-before.png) 

    <span data-ttu-id="df703-212">Nachher:</span><span class="sxs-lookup"><span data-stu-id="df703-212">After:</span></span>

    ![Deaktivierter Text nach der Verbesserung der Barrierefreiheit](media/wf-disabled-after.png) 

- <span data-ttu-id="df703-214">Verbesserungen am Design mit hohem Kontrast im Dialogfeld der Threadausnahme.</span><span class="sxs-lookup"><span data-stu-id="df703-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="df703-215">**Verbesserte Unterstützung für die Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="df703-215">**Improved Narrator support**</span></span>

<span data-ttu-id="df703-216">Windows Forms in .NET Framework 4.7.1 enthält folgende Verbesserungen für die Barrierefreiheit der Sprachausgabe:</span><span class="sxs-lookup"><span data-stu-id="df703-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="df703-217">Auf das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann über die Sprachausgabe sowie über andere Tools zur Automatisierung der Benutzeroberfläche zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="df703-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="df703-218">Das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement teilt der Sprachausgabe mit, wenn der Aktivierungszustand eines Elements geändert wurde, sodass der Benutzer darüber benachrichtigt wird, dass der Wert eines Listenelements verändert wurde.</span><span class="sxs-lookup"><span data-stu-id="df703-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="df703-219">Das <xref:System.Windows.Forms.DataGridViewCell>-Steuerelement teilt der Sprachausgabe den richtigen schreibgeschützten Status mit.</span><span class="sxs-lookup"><span data-stu-id="df703-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="df703-220">Die Sprachausgabe kann nun deaktivierten <xref:System.Windows.Forms.ToolStripMenuItem>-Text ausgeben, während deaktivierte Menüelemente zuvor übersprungen wurden.</span><span class="sxs-lookup"><span data-stu-id="df703-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="df703-221">**Verbesserte Unterstützung für die Barrierefreiheitsmuster der UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="df703-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="df703-222">Ab .NET Framework 4.7.1 können die Entwickler von Tools für Barrierefreiheitstechnologien allgemeine API-Barrierefreiheitsmuster und -eigenschaften für mehrere WinForms-Steuerelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="df703-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="df703-223">Folgende Verbesserungen der Barrierefreiheit wurden vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="df703-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="df703-224">Die <xref:System.Windows.Forms.ComboBox>- und <xref:System.Windows.Forms.ToolStripSplitButton>-Steuerelemente unterstützen nun das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="df703-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="df703-225">Das <xref:System.Windows.Forms.DataGridViewCheckBoxCell>-Steuerelement unterstützt nun das [Umschaltmuster](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="df703-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="df703-226">Das <xref:System.Windows.Forms.ToolStripItem>-Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft und das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="df703-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="df703-227">Die <xref:System.Windows.Forms.NumericUpDown>- und <xref:System.Windows.Forms.DomainUpDown>-Steuerelemente unterstützen die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="df703-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="df703-228">**Verbesserter Eigenschaftenbrowser**</span><span class="sxs-lookup"><span data-stu-id="df703-228">**Improved property browser experience**</span></span>

<span data-ttu-id="df703-229">Ab .NET Framework 4.7.1 enthält Windows Forms Folgendes:</span><span class="sxs-lookup"><span data-stu-id="df703-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="df703-230">Eine verbesserte Tastaturnavigation durch die verschiedenen Fenster der Dropdownauswahl</span><span class="sxs-lookup"><span data-stu-id="df703-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="df703-231">Eine Verringerung unnötiger Tabstopps</span><span class="sxs-lookup"><span data-stu-id="df703-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="df703-232">Eine verbesserte Berichterstellung der Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="df703-232">Better reporting of control types.</span></span>
- <span data-ttu-id="df703-233">Ein verbessertes Verhalten der Sprachausgabe</span><span class="sxs-lookup"><span data-stu-id="df703-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="df703-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df703-234">See Also</span></span>
[<span data-ttu-id="df703-235">What's new in the .NET Framework (Neuerungen in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="df703-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 