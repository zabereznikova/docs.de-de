---
title: Was ist neu in Barrierefreiheit in .NET Framework
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
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="65c07-102">Was ist neu in Barrierefreiheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="65c07-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="65c07-103">.NET Framework zielt darauf ab, zu Anwendungen Weitere Accessibile für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="65c07-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="65c07-104">Barrierefreiheitsfunktionen ermöglichen eine Anwendung in eine entsprechende Erfahrung für Benutzer der Hilfstechnologie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="65c07-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="65c07-105">Ab .NET Framework 4.7.1 enthält .NET Framework eine große Anzahl von Eingabehilfen-Verbesserungen, die Entwicklern das Erstellen von Anwendungen mit Barrierefreiheit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="65c07-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="65c07-106">Die neuen Funktionen für Barrierefreiheit sind standardmäßig für Anwendungen, die das .NET 4.7.1 Framework enabled "oder" weiter unten.</span><span class="sxs-lookup"><span data-stu-id="65c07-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="65c07-107">Darüber hinaus Anwendungen, die auf eine frühere Version von .NET Framework, jedoch auf .NET Framework 4.7.1 ausgeführt werden oder später entscheiden können, ältere Eingabehilfen-Verhalten (und somit entscheiden Sie sich für die Barrierefreiheit Verbesserungen in .NET Framework 4.7.1) durch Hinzufügen des folgenden Switches, die [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) Abschnitt der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="65c07-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="65c07-108">Auf ähnliche Weise können Anwendungen, die gezielt Versionen von .NET Framework 4.7.1 ab Barrierefreiheitsfunktionen deaktivieren, indem Sie die folgenden Schalter zum Hinzufügen der [ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) Element in der [ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md) Abschnitt der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="65c07-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="65c07-109">Neuigkeiten in .NET Framework 4.7.1 Eingabehilfe</span><span class="sxs-lookup"><span data-stu-id="65c07-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="65c07-110">.NET Framework 4.7.1 enthält neue Features für Eingabehilfen in den folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="65c07-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="65c07-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="65c07-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="65c07-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="65c07-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="65c07-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="65c07-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="65c07-114">**Bildschirm Reader Verbesserungen**</span><span class="sxs-lookup"><span data-stu-id="65c07-114">**Screen reader improvements**</span></span>

<span data-ttu-id="65c07-115">Wenn Barrierefreiheit Verbesserungen aktiviert sind, enthält .NET Framework 4.7.1 die folgenden Verbesserungen, die Bildschirmsprachausgaben beeinflussen:</span><span class="sxs-lookup"><span data-stu-id="65c07-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="65c07-116">In .NET Framework 4.7 und früheren Versionen <xref:System.Windows.Controls.Expander> Steuerelemente von Bildschirmsprachausgaben als Schaltflächen angekündigt wurden.</span><span class="sxs-lookup"><span data-stu-id="65c07-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="65c07-117">Ab .NET Framework 4.7.1, werden sie ordnungsgemäß als erweiterbaren/reduzierbaren Gruppen angekündigt.</span><span class="sxs-lookup"><span data-stu-id="65c07-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="65c07-118">In .NET Framework 4.7 und früheren Versionen <xref:System.Windows.Controls.DataGridCell> Steuerelemente von Bildschirmsprachausgaben angekündigt wurden, als "Benutzerdefiniert".</span><span class="sxs-lookup"><span data-stu-id="65c07-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="65c07-119">Ab .NET Framework 4.7.1, werden sie jetzt ordnungsgemäß als Raster Datenzelle (lokalisiert) angekündigt.</span><span class="sxs-lookup"><span data-stu-id="65c07-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="65c07-120">Ab .NET Framework 4.7.1, ankündigen Sprachausgaben den Namen einer bearbeitbaren <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="65c07-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="65c07-121">In .NET Framework 4.7 und früheren Versionen <xref:System.Windows.Controls.PasswordBox> Steuerelemente wurden als "kein Element in der Ansicht" angekündigt wird, oder hatte fehlerhafte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="65c07-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="65c07-122">Dieses Problem ist behoben, beginnend mit .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="65c07-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="65c07-123">**UIAutomation LiveRegion-Unterstützung**</span><span class="sxs-lookup"><span data-stu-id="65c07-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="65c07-124">Sprachausgabe, z. B. Sprachausgabe Hilfe Personen lesen den Inhalt der Benutzeroberfläche einer Anwendung in der Regel von-Sprach-Ausgabe von UI-Inhalten, die Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="65c07-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="65c07-125">Jedoch, wenn ein Element der Benutzeroberfläche ändert und verfügt nicht über den Fokus, und der Benutzer möglicherweise nicht benachrichtigt werden wichtige Informationen verstößt.</span><span class="sxs-lookup"><span data-stu-id="65c07-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="65c07-126">Live-Regionen Ziel der Lösung dieses Problems.</span><span class="sxs-lookup"><span data-stu-id="65c07-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="65c07-127">Entwickler können sie um zu informieren, die Bildschirmsprachausgaben oder einem anderen UIAutomation-Client, den auf ein Element der Benutzeroberfläche eine wichtige Änderung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="65c07-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="65c07-128">Die Sprachausgabe kann dann entscheiden, wie und wann auf die Benutzer über diese Änderung zu informieren.</span><span class="sxs-lookup"><span data-stu-id="65c07-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="65c07-129">Um live Regionen zu unterstützen, wurden die folgenden APIs in WPF hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="65c07-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="65c07-130">Die <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> und <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> Felder, die Identifizieren der **LiveSetting** Eigenschaft und die **LiveRegionChanged** Ereignis.</span><span class="sxs-lookup"><span data-stu-id="65c07-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="65c07-131">Sie können mit XAML festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="65c07-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="65c07-132">Die **AutomationProperties.LiveSetting** angefügten Eigenschaft, die die Bildschirmsprachausgaben die Wichtigkeit der UI-Änderung an den Benutzer darüber informiert.</span><span class="sxs-lookup"><span data-stu-id="65c07-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="65c07-133">Die <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> -Eigenschaft, die identifiziert die **AutomationProperties.LiveSetting** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="65c07-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="65c07-134">Die <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> -Methode, die überschrieben werden kann, ermöglichen eine **LiveSetting** Wert.</span><span class="sxs-lookup"><span data-stu-id="65c07-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="65c07-135">Die <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> und <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> -Methoden, die abrufen und Festlegen einer **LiveSetting** Wert.</span><span class="sxs-lookup"><span data-stu-id="65c07-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="65c07-136">Die <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> -Enumeration, die die folgenden möglichen definiert **LiveSetting** Werte:</span><span class="sxs-lookup"><span data-stu-id="65c07-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="65c07-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65c07-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65c07-138">Das Element ist keine Benachrichtigungen gesendet werden, wenn der Inhalt des aktiven Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="65c07-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="65c07-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65c07-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65c07-140">Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="65c07-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="65c07-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65c07-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65c07-142">Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="65c07-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="65c07-143">Sie können eine LiveRegion erstellen, durch Festlegen der **AutomationProperties.LiveSetting** -Eigenschaft des Elements von Interesse sind, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="65c07-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="65c07-144">Wenn die Daten in den aktiven Bereich ändern und Sie eine Bildschirmsprachausgabe informieren müssen, lösen Sie explizit ein Ereignis, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="65c07-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="65c07-145">**Hoher Kontrast**</span><span class="sxs-lookup"><span data-stu-id="65c07-145">**High contrast**</span></span>

<span data-ttu-id="65c07-146">Beginnend mit .NET Framework 4.7.1, Verbesserungen bei hohem Kontrast verschiedene WPF-Steuerelemente wurden.</span><span class="sxs-lookup"><span data-stu-id="65c07-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="65c07-147">Sie sind jetzt sichtbar, wenn die <xref:System.Windows.SystemParameters.HighContrast%2A> Design "festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="65c07-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="65c07-148">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="65c07-148">These include:</span></span>

- <span data-ttu-id="65c07-149"><xref:System.Windows.Controls.Expander>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65c07-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="65c07-150">Der Schwerpunkt für visual der <xref:System.Windows.Controls.Expander> -Steuerelement ist nun sichtbar.</span><span class="sxs-lookup"><span data-stu-id="65c07-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="65c07-151">Die Tastatur visuellen Elemente für <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, und <xref:System.Windows.Controls.RadioButton> Steuerelemente werden ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65c07-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="65c07-152">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65c07-152">For example:</span></span>

    <span data-ttu-id="65c07-153">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-153">Before:</span></span> 
    
    ![Expandersteuerelement mit Fokus vor Eingabehilfen-Verbesserungen](media/expander-before.png)

    <span data-ttu-id="65c07-155">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-155">After:</span></span> 

    ![Expandersteuerelement mit Fokus nach Eingabehilfen-Verbesserungen](media/expander-after.png)

- <span data-ttu-id="65c07-157"><xref:System.Windows.Controls.CheckBox>und <xref:System.Windows.Controls.RadioButton> Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="65c07-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="65c07-158">Der Text in der <xref:System.Windows.Controls.CheckBox> und <xref:System.Windows.Controls.RadioButton> Steuerelemente ist jetzt leichter zu erkennen, wenn Sie in Designs mit hohem Kontrast auswählen.</span><span class="sxs-lookup"><span data-stu-id="65c07-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="65c07-159">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65c07-159">For example:</span></span>

    <span data-ttu-id="65c07-160">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-160">Before:</span></span> 

    ![Hoher Kontrast Optionsfeld den Fokus hat, vor dem Zugriff auf Verbesserungen](media/radio-button-before.png)
    
    <span data-ttu-id="65c07-162">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-162">After:</span></span> 

    ![Hoher Kontrast Optionsfeld mit dem Fokus nach Eingabehilfen-Verbesserungen](media/radio-button-after.png)

- <span data-ttu-id="65c07-164"><xref:System.Windows.Controls.ComboBox>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65c07-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="65c07-165">Ab .NET Framework 4.7.1, den Rahmen einen deaktivierten <xref:System.Windows.Controls.ComboBox> -Steuerelement ist die gleiche Farbe wie deaktiviertem Text.</span><span class="sxs-lookup"><span data-stu-id="65c07-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="65c07-166">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65c07-166">For example:</span></span>
    
    <span data-ttu-id="65c07-167">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-167">Before:</span></span> 

     ![ComboBox deaktiviert, Rahmen und Text vor dem Eingabehilfen-Verbesserungen](media/combo-disabled-before.png)

    <span data-ttu-id="65c07-169">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-169">After:</span></span>   

     ![Rahmen und Text deaktiviert nach Eingabehilfen Verbesserungen ComboBox](media/combo-disabled-after.png)

    <span data-ttu-id="65c07-171">Darüber hinaus verwenden deaktivierte und konzentriert sich Schaltflächen die richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="65c07-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="65c07-172">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-172">Before:</span></span>

    ![Schaltfläche Designfarben vor Eingabehilfen-Verbesserungen](media/button-themes-before.png) 
    
    <span data-ttu-id="65c07-174">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-174">After:</span></span> 

    ![Schaltfläche Designfarben nach Eingabehilfen-Verbesserungen](media/button-themes-after.png) 

    <span data-ttu-id="65c07-176">Schließlich in der .NET Framework 4.7 und frühere Versionen, die Einstellung einer <xref:System.Windows.Controls.ComboBox> Steuerelementformats zu `Toolbar.ComboBoxStyleKey` verursacht den Dropdown Pfeil unsichtbar.</span><span class="sxs-lookup"><span data-stu-id="65c07-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="65c07-177">Dieses Problem ist behoben, beginnend mit .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="65c07-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="65c07-178">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65c07-178">For example:</span></span>

    <span data-ttu-id="65c07-179">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey vor Eingabehilfen-Verbesserungen](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="65c07-181">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey nach Eingabehilfen-Verbesserungen](media/comboboxstylekey-after.png) 

- <span data-ttu-id="65c07-183"><xref:System.Windows.Controls.DataGrid>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="65c07-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="65c07-184">Ab .NET Framework 4.7.1, die Sortierreihenfolge Indikator Pfeil in <xref:System.Windows.Controls.DataGrid> steuert nun verwendet Designfarben korrigieren.</span><span class="sxs-lookup"><span data-stu-id="65c07-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="65c07-185">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65c07-185">For example:</span></span>

    <span data-ttu-id="65c07-186">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-186">Before:</span></span> 

    ![Sortieren von Indikator Pfeile neben den Eingabehilfen-Verbesserungen](media/sort-indicator-before.png) 
    
    <span data-ttu-id="65c07-188">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-188">After:</span></span>   
 
    ![Sortieren von Indikator Pfeil nach Eingabehilfen-Verbesserungen](media/sort-indicator-after.png) 
    
    <span data-ttu-id="65c07-190">Darüber hinaus geändert in .NET Framework 4.7 und früheren Versionen müssen der Standardstil für den Link auf eine falsche Farbe auf Maus über im Modus für hohen Kontrast.</span><span class="sxs-lookup"><span data-stu-id="65c07-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="65c07-191">Dies ist die beginnen mit .NET Framework 4.7.1 aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="65c07-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="65c07-192">Auf ähnliche Weise <xref:System.Windows.Controls.DataGrid> Kontrollkästchen Spalten die erwarteten Farben für Tastatur Fokus Feedback beginnend mit .NET Framework 4.7.1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="65c07-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="65c07-193">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-193">Before:</span></span> 

    ![Link DataGrid-Standardformat vor Eingabehilfen-Verbesserungen](media/default-link-style-before.png) 
 
    <span data-ttu-id="65c07-195">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-195">After:</span></span>    
  
    ![Link DataGrid-Standardformat nach Eingabehilfen-Verbesserungen](media/default-link-style-after.png)  

<span data-ttu-id="65c07-197">Weitere Informationen zu den Eingabehilfen-Verbesserungen für WPF in .NET Framework 4.7.1 finden Sie unter [Eingabehilfen-Verbesserungen in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="65c07-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="65c07-198">Verbesserungen für Windows Forms-Eingabehilfen</span><span class="sxs-lookup"><span data-stu-id="65c07-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="65c07-199">In .NET Framework, 4.7.1 umfasst Windows Forms (WinForms) Zugriff auf Änderungen in den folgenden Bereichen.</span><span class="sxs-lookup"><span data-stu-id="65c07-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="65c07-200">**Verbesserte Anzeige im Modus für hohe Kontraste**</span><span class="sxs-lookup"><span data-stu-id="65c07-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="65c07-201">Ab .NET Framework 4.7.1, bieten verschiedene WinForms-Steuerelemente verbesserte Renderingerweiterungen in den Modi für hoher Kontrast im Betriebssystem verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65c07-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="65c07-202">Windows 10 die Werte für einige hoher Kontrast Systemfarben geändert wurde, und Windows Forms basiert auf Windows 10-Win32-Framework.</span><span class="sxs-lookup"><span data-stu-id="65c07-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="65c07-203">Optimale Ergebnisse zu erzielen führen Sie die neueste Version von Windows, und entscheiden Sie sich mit den aktuellen OS-Änderungen, indem Sie das Hinzufügen einer Datei "app.manifest" in einer testanwendung und Windows 10-Kommentar OS Zeile unterstützt, damit es im folgenden wird erläutert:</span><span class="sxs-lookup"><span data-stu-id="65c07-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="65c07-204">Einige Beispiele für hohen Kontrast Änderungen:</span><span class="sxs-lookup"><span data-stu-id="65c07-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="65c07-205">Häkchen im <xref:System.Windows.Forms.MenuStrip> Elemente sind einfacher zu anzeigen.</span><span class="sxs-lookup"><span data-stu-id="65c07-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="65c07-206">Bei Auswahl dieser Option deaktiviert <xref:System.Windows.Forms.MenuStrip> Elemente sind einfacher zu anzeigen.</span><span class="sxs-lookup"><span data-stu-id="65c07-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="65c07-207">Text in einem ausgewählten <xref:System.Windows.Forms.Button> Gegensatz die Auswahlfarbe steuern.</span><span class="sxs-lookup"><span data-stu-id="65c07-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="65c07-208">Deaktivierter Text ist einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="65c07-208">Disabled text is easier to read.</span></span> <span data-ttu-id="65c07-209">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65c07-209">For example:</span></span>

    <span data-ttu-id="65c07-210">Vorher:</span><span class="sxs-lookup"><span data-stu-id="65c07-210">Before:</span></span>

    ![Deaktiviertem Text vor dem Eingabehilfen-Verbesserungen](media/wf-disabled-before.png) 

    <span data-ttu-id="65c07-212">Nachher:</span><span class="sxs-lookup"><span data-stu-id="65c07-212">After:</span></span>

    ![Deaktivierte Text nach Eingabehilfen-Verbesserungen](media/wf-disabled-after.png) 

- <span data-ttu-id="65c07-214">Hoher Kontrast Verbesserungen im Thread-Dialogfeld "Ausnahme".</span><span class="sxs-lookup"><span data-stu-id="65c07-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="65c07-215">**Verbesserte Unterstützung für die Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="65c07-215">**Improved Narrator support**</span></span>

<span data-ttu-id="65c07-216">Windows Forms in .NET Framework 4.7.1 umfasst die folgenden Eingabehilfen-Verbesserungen für die Sprachausgabe:</span><span class="sxs-lookup"><span data-stu-id="65c07-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="65c07-217">Die <xref:System.Windows.Forms.MonthCalendar> Steuerelement möglich, die von der Sprachausgabe sowie von anderen Automatisierungstools UI.</span><span class="sxs-lookup"><span data-stu-id="65c07-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="65c07-218">Die <xref:System.Windows.Forms.CheckedListBox> Steuerelement Sprachausgabe benachrichtigt, wenn der Aktivierungszustand eines Elements geändert wurde, damit der Benutzer informiert wird, dass sie den Wert eines Listenelement geändert haben.</span><span class="sxs-lookup"><span data-stu-id="65c07-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="65c07-219">Die <xref:System.Windows.Forms.DataGridViewCell> Steuerelement des korrekten Status der nur-Lese Sprachausgabe meldet.</span><span class="sxs-lookup"><span data-stu-id="65c07-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="65c07-220">Sprachausgabe kann nun deaktiviert lesen <xref:System.Windows.Forms.ToolStripMenuItem> Text, wohingegen zuvor es deaktiviert Menüelemente überspringen möchten.</span><span class="sxs-lookup"><span data-stu-id="65c07-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="65c07-221">**Verbesserte Unterstützung für UIAutomation Eingabehilfen-Muster**</span><span class="sxs-lookup"><span data-stu-id="65c07-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="65c07-222">Ab .NET Framework 4.7.1, können Entwickler von Eingabehilfen-Technologie häufige Muster von API-Zugriff und die Eigenschaften für mehrere WinForms-Steuerelemente nutzen.</span><span class="sxs-lookup"><span data-stu-id="65c07-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="65c07-223">Diese Eingabehilfen Verbesserungen umfassen:</span><span class="sxs-lookup"><span data-stu-id="65c07-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="65c07-224">Die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ToolStripSplitButton> unterstützen jetzt die [erweitern/reduzieren-Muster](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="65c07-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="65c07-225">Die <xref:System.Windows.Forms.DataGridViewCheckBoxCell> unterstützt jetzt die [Toggle-Muster](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="65c07-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="65c07-226">Die <xref:System.Windows.Forms.ToolStripItem> -Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.Name> Eigenschaft und die [erweitern/reduzieren-Muster](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="65c07-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="65c07-227">Die <xref:System.Windows.Forms.NumericUpDown> und <xref:System.Windows.Forms.DomainUpDown> Steuerelemente unterstützen die <xref:System.Windows.Automation.automationElement.Name> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="65c07-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.automationElement.Name> property.</span></span>

<span data-ttu-id="65c07-228">**Verbesserte Eigenschaft Browserfunktionen**</span><span class="sxs-lookup"><span data-stu-id="65c07-228">**Improved property browser experience**</span></span>

<span data-ttu-id="65c07-229">Ab .NET Framework 4.7.1, umfasst Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="65c07-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="65c07-230">Eine bessere Tastaturnavigation durch die verschiedenen Dropdownfeld-Fenster.</span><span class="sxs-lookup"><span data-stu-id="65c07-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="65c07-231">Eine Verringerung unnötiger Tabstopps.</span><span class="sxs-lookup"><span data-stu-id="65c07-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="65c07-232">Melden besser von Steuerelementtypen.</span><span class="sxs-lookup"><span data-stu-id="65c07-232">Better reporting of control types.</span></span>
- <span data-ttu-id="65c07-233">Verbesserte Sprachausgabe Verhalten.</span><span class="sxs-lookup"><span data-stu-id="65c07-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="65c07-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65c07-234">See Also</span></span>
[<span data-ttu-id="65c07-235">Was ist neu in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="65c07-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 