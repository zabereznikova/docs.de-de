---
title: 'Neuerungen der Barrierefreiheit in .NET Framework '
titleSuffix: ''
description: Hier erfahren Sie, welche Neuigkeiten es bei der Barrierefreiheit in .NET ab .NET Framework 4.7.1 gibt. Barrierefreiheitsfeatures ermöglichen es, dass eine App genau die Servicequalität bietet, die für Benutzer von Hilfstechnologien erforderlich ist.
ms.date: 01/05/2021
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: c2ebaed8bf347eb8d8764f4bdf76dcc33db86bad
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536163"
---
# <a name="whats-new-in-accessibility-in-net-framework"></a><span data-ttu-id="f4d6c-104">Neuerungen der Barrierefreiheit in .NET Framework </span><span class="sxs-lookup"><span data-stu-id="f4d6c-104">What's new in accessibility in .NET Framework</span></span>

<span data-ttu-id="f4d6c-105">Mit dem .NET Framework entwickelte Anwendungen bieten mehr Barrierefreiheit für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-105">.NET Framework aims to make applications more accessible for your users.</span></span> <span data-ttu-id="f4d6c-106">Durch Barrierefreiheitsfunktionen wird es einer Anwendung ermöglicht, den Benutzern von Hilfstechnologien ein angemessenes Erlebnis zu bieten.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-106">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="f4d6c-107">Ab .NET Framework 4.7.1 enthält das .NET Framework zahlreiche Verbesserungen hinsichtlich der Barrierefreiheit, die es Entwicklern ermöglichen, barrierefreie Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-107">Starting with .NET Framework 4.7.1, .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="f4d6c-108">Barrierefreiheitsparameter</span><span class="sxs-lookup"><span data-stu-id="f4d6c-108">Accessibility switches</span></span>

<span data-ttu-id="f4d6c-109">Wenn Ihre App auf .NET Framework 4.7 oder niedriger ausgerichtet ist, aber auf .NET Framework 4.7.1 oder höher ausgeführt wird, können Sie sie für Barrierefreiheitsfeatures konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-109">You can configure your app to opt into accessibility features if it targets .NET Framework 4.7 or an earlier version but is running on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="f4d6c-110">Sie können auch Ihre App für Legacy-Features konfigurieren (und Barrierefreiheitsfeatures außen vor lassen), wenn diese auf .NET Framework 4.7.1 oder höher ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-110">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="f4d6c-111">Jede .NET Framework-Version, die Barrierefreiheitsfeatures umfasst, verfügt über einen versionsspezifischen Barrierefreiheitsparameter, den Sie dem [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im Abschnitt [`<runtime>`](../configure-apps/file-schema/runtime/index.md) der Anwendungskonfigurationsdatei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-111">Each .NET Framework version that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="f4d6c-112">Die folgenden Parameter werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-112">The following are the supported switches:</span></span>

|<span data-ttu-id="f4d6c-113">Version</span><span class="sxs-lookup"><span data-stu-id="f4d6c-113">Version</span></span>|<span data-ttu-id="f4d6c-114">Schalter</span><span class="sxs-lookup"><span data-stu-id="f4d6c-114">Switch</span></span>|
|---|---|
|<span data-ttu-id="f4d6c-115">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f4d6c-115">.NET Framework 4.7.1</span></span>|<span data-ttu-id="f4d6c-116">„Switch.UseLegacyAccessibilityFeatures“</span><span class="sxs-lookup"><span data-stu-id="f4d6c-116">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="f4d6c-117">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="f4d6c-117">.NET Framework 4.7.2</span></span>|<span data-ttu-id="f4d6c-118">„Switch.UseLegacyAccessibilityFeatures.2“</span><span class="sxs-lookup"><span data-stu-id="f4d6c-118">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|
|<span data-ttu-id="f4d6c-119">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f4d6c-119">.NET Framework 4.8</span></span>|<span data-ttu-id="f4d6c-120">"Switch.UseLegacyAccessibilityFeatures.3"</span><span class="sxs-lookup"><span data-stu-id="f4d6c-120">"Switch.UseLegacyAccessibilityFeatures.3"</span></span>|
|<span data-ttu-id="f4d6c-121">11. August 2020: Kumulatives Update KB4569746 für .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f4d6c-121">August 11, 2020-KB4569746 Cumulative Update for .NET Framework 4.8</span></span>|<span data-ttu-id="f4d6c-122">"Switch.UseLegacyAccessibilityFeatures.4"</span><span class="sxs-lookup"><span data-stu-id="f4d6c-122">"Switch.UseLegacyAccessibilityFeatures.4"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="f4d6c-123">Profitieren von Barrierefreiheitserweiterungen</span><span class="sxs-lookup"><span data-stu-id="f4d6c-123">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="f4d6c-124">Die neuen Barrierefreiheitsfunktionen werden standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-124">The new accessibility features are enabled by default for applications that target .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="f4d6c-125">Zusätzlich können Anwendungen, die eine frühere Version von .NET Framework anzielen, aber unter .NET Framework 4.7.1 oder höher ausgeführt werden, veraltete Verhaltensweisen für die Barrierefreiheit deaktivieren (und dadurch die Verbesserungen der Barrierefreiheit nutzen), indem Sie dem [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](../configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung einen Parameter hinzufügen und deren Wert auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-125">In addition, applications that target an earlier version of the .NET Framework but are running on .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="f4d6c-126">Der folgende Codeausschnitt veranschaulicht, wie Sie die in .NET Framework 4.7.1 eingeführten Barrierefreiheitsverbesserungen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-126">The following snippet shows how to opt in to the accessibility enhancements that were introduced in .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="f4d6c-127">Wenn Sie die Barrierefreiheitsoptionen in einer höheren Version des .NET Framework aktivieren, müssen Sie ebenfalls die Features früherer Versionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-127">If you choose to opt in to accessibility features in a later .NET Framework version, you must also explicitly opt in to the features from earlier versions.</span></span> <span data-ttu-id="f4d6c-128">Sie müssen das folgende [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element hinzufügen, um Ihre App so zu konfigurieren, dass Sie die Verbesserungen der Barrierefreiheit sowohl in .NET Framework 4.7.1 als auch in Version 4.7.2 nutzen können:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-128">To configure your app to take advantage of accessibility improvements in both .NET Framework 4.7.1 and 4.7.2, add the the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

<span data-ttu-id="f4d6c-129">Sie müssen das folgende [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element hinzufügen, um Ihre App so zu konfigurieren, dass Sie die Verbesserungen hinsichtlich der Barrierefreiheit in NET Framework 4.7.1, 4.7.2, 4.8 und das kumulative Update von August 2020 für .NET Framework 4.8 nutzen können:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-129">To configure your app to take advantage of accessibility improvements in .NET Framework 4.7.1, 4.7.2, 4.8, and the August 2020 cumulative update for .NET Framework 4.8, add the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value=Switch.UseLegacyAccessibilityFeatures=false|Switch.UseLegacyAccessibilityFeatures.2=false|Switch.UseLegacyAccessibilityFeatures.3=false|Switch.UseLegacyAccessibilityFeatures.4=false"/>
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="f4d6c-130">Wiederherstellen von Legacyverhalten</span><span class="sxs-lookup"><span data-stu-id="f4d6c-130">Restoring legacy behavior</span></span>

<span data-ttu-id="f4d6c-131">Für Anwendungen, die mindestens auf .NET Framework 4.7.1 ausgelegt sind, können die Barrierefreiheitsfeatures deaktiviert werden, indem folgende Optionen mit dem Wert `true` zum [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](../configure-apps/file-schema/runtime/index.md)-Abschnitt der Anwendungskonfigurationsdatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-131">Applications that target versions of .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="f4d6c-132">Beispielsweise deaktiviert die folgende Konfiguration die Barrierefreiheitsfeatures, die in .NET Framework 4.7.2 eingeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-132">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-august-11-2020-cumulative-update-for-net-framework-48"></a><span data-ttu-id="f4d6c-133">Neuerungen bei den Barrierefreiheitsfeatures im kumulativen Update für .NET Framework 4.8 vom 11. August 2020</span><span class="sxs-lookup"><span data-stu-id="f4d6c-133">What's new in accessibility in the August 11, 2020 Cumulative Update for .NET Framework 4.8</span></span>

<span data-ttu-id="f4d6c-134">Das kumulative Update KB4569746 für .NET Framework 4.8 vom 11. August 2020 führt neue Barrierefreiheitsfeatures für Windows Forms ein:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-134">The August 11, 2020-KB4569746 Cumulative Update for .NET Framework 4.8 includes new accessibility features in Windows Forms:</span></span>

- <span data-ttu-id="f4d6c-135">Ein Problem mit der Sprachausgabe von `PropertyGrid`-Steuerelementen und dem Status von Kategorien (aufgeklappt/zugeklappt) wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-135">Addresses an issue with announcing `PropertyGrid` control items and a category's expanded/collapsed state by screen readers.</span></span>

- <span data-ttu-id="f4d6c-136">Die Barrierefreiheitsmuster des Steuerelements `PropertyGrid` und dessen inneren Elementen wurden aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-136">Updates the accessible patterns of the `PropertyGrid` control and its inner elements.</span></span>

- <span data-ttu-id="f4d6c-137">Die barrierefreien Namen der inneren Elemente des Steuerelements `PropertyGrid` wurden aktualisiert und werden nun korrekt von der Sprachausgabe wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-137">Updates the accessible names of the `PropertyGrid` control inner elements so they're correctly announced by screen readers.</span></span>

- <span data-ttu-id="f4d6c-138">Ein Problem mit Begrenzungsrahmen für barrierefreie Eigenschaften des Steuerelements `PropertyGridView` wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-138">Addresses bounding rectangle accessible properties for the `PropertyGridView` controls.</span></span>

- <span data-ttu-id="f4d6c-139">Die Sprachausgabe gibt den Status der Zellen des Kombinationsfelds `DataGridView` (aufgeklappt/zugeklappt) jetzt korrekt wieder.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-139">Enables screen readers to correctly announce the expanded/collapsed state of `DataGridView` combo box cells.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-48"></a><span data-ttu-id="f4d6c-140">Neuerungen der Barrierefreiheit in .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="f4d6c-140">What's new in accessibility in .NET Framework 4.8</span></span>

<span data-ttu-id="f4d6c-141">.NET Framework 4.8 enthält neue Barrierefreiheitsfunktionen für die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-141">.NET Framework 4.8 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="f4d6c-142">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4d6c-142">Windows Forms</span></span>](#winforms48)

- [<span data-ttu-id="f4d6c-143">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-143">Windows Presentation Foundation (WPF)</span></span>](#wpf48)

- [<span data-ttu-id="f4d6c-144">Workflow-Designer von Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-144">Windows Workflow Foundation (WF) workflow designer</span></span>](#wf48)

<a name="winforms48"></a>

### <a name="windows-forms"></a><span data-ttu-id="f4d6c-145">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4d6c-145">Windows Forms</span></span>

<span data-ttu-id="f4d6c-146">In .NET Framework 4.8 bieten Windows Forms jetzt Unterstützung für LiveRegions und Benachrichtigungsereignisse für viele häufig verwendete Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-146">In .NET Framework 4.8, Windows Forms adds support for LiveRegions and Notification Events to many commonly used controls.</span></span> <span data-ttu-id="f4d6c-147">Es bietet auch Unterstützung für QuickInfos, wenn ein Benutzer mit der Tastatur zu einem Steuerelement navigiert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-147">It also adds support for ToolTips when a user navigates to a control by using the keyboard.</span></span>

<span data-ttu-id="f4d6c-148">**Unterstützung für UIA-LiveRegions in den Bezeichnungen und StatusStrips**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-148">**UIA LiveRegions Support in Labels and StatusStrips**</span></span>

<span data-ttu-id="f4d6c-149">UIA LiveRegions ermöglichen es Anwendungsentwicklern, Sprachausgaben über eine Textänderung in einem Steuerelement zu informieren, das sich außerhalb des Bereichs befindet, in dem der Benutzer arbeitet.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-149">UIA LiveRegions allow application developers to notify screen readers of a text change in a control that is located apart from the location where the user is working.</span></span> <span data-ttu-id="f4d6c-150">Dies ist z.B. für ein <xref:System.Windows.Forms.StatusStrip>-Steuerelement nützlich, das einen Verbindungsstatus anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-150">This is useful, for example, for a <xref:System.Windows.Forms.StatusStrip> control that shows a connection status.</span></span> <span data-ttu-id="f4d6c-151">Wenn die Verbindung unterbrochen wird und sich der Status ändert, kann der Entwickler die Sprachausgabe benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-151">If the connection is dropped and the status changes, the developer might want to notify the screen reader.</span></span>

<span data-ttu-id="f4d6c-152">Ab .NET Framework 4.8 implementiert Windows Forms UIA-LiveRegions für sowohl <xref:System.Windows.Forms.Label>- als auch <xref:System.Windows.Forms.StatusStrip>-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-152">Starting with .NET Framework 4.8, Windows Forms implements UIA LiveRegions for both the <xref:System.Windows.Forms.Label> and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="f4d6c-153">Der folgende Code verwendet die LiveRegion beispielsweise in einem <xref:System.Windows.Forms.Label>-Steuerelement mit dem Namen `label1`:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-153">For example, the following code uses the LiveRegion in a <xref:System.Windows.Forms.Label> control named `label1`:</span></span>

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

<span data-ttu-id="f4d6c-154">Die Sprachausgabe kündigt „Bereit“ an, unabhängig davon, wo der Benutzer mit der Anwendung gerade interagiert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-154">Narrator announces “Ready” regardless of where the user is interacting with the application.</span></span>

<span data-ttu-id="f4d6c-155">Sie können Ihr <xref:System.Windows.Forms.UserControl> ebenfalls als LiveRegion implementieren:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-155">You can also implement your <xref:System.Windows.Forms.UserControl> as a LiveRegion:</span></span>

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

<span data-ttu-id="f4d6c-156">**UIA-Benachrichtigungsereignisse**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-156">**UIA notification events**</span></span>

<span data-ttu-id="f4d6c-157">Das UIA-Benachrichtigungsereignis, das mit dem Windows 10 Fall Creators Update eingeführt wurde, ermöglicht es Ihrer App, ein UIA-Ereignis auszulösen, was dazu führt, dass die Sprachausgabe einfach eine Ankündigung basierend auf dem Text macht, den Sie mit dem Ereignis bereitstellen. Dafür muss in der Benutzeroberfläche kein entsprechendes Steuerelement vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-157">The UIA Notification event, introduced in Windows 10 Fall Creators Update, allows your app to raise a UIA event, which leads to Narrator simply making an announcement based on text you supply with the event, without the need to have a corresponding control in the UI.</span></span> <span data-ttu-id="f4d6c-158">In einigen Szenarien ist dies eine einfache Möglichkeit, um die Barrierefreiheit Ihrer App erheblich zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-158">In some scenarios, this is a straightforward way to dramatically improve the accessibility of your app.</span></span> <span data-ttu-id="f4d6c-159">Auch kann damit über den Fortschritt eines Prozesses zu informiert werden, der viel Zeit in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-159">In can also be useful to notify of the progress of some process that may take a long time.</span></span> <span data-ttu-id="f4d6c-160">Weitere Informationen über UIA-Benachrichtigungsereignisse finden Sie in [Can your desktop app leverage the new UI Notification event?](/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need) (Kann Ihre Desktop-App das neue UI-Benachrichtigungsereignis nutzen?).</span><span class="sxs-lookup"><span data-stu-id="f4d6c-160">For more information about UIA Notification Events, see [Can your desktop app leverage the new UI Notification event?](/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need).</span></span>

<span data-ttu-id="f4d6c-161">Im folgenden Beispiel wird ein [Benachrichtigungsereignis](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A) ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-161">The following example raises the [Notification event](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span></span>

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

<span data-ttu-id="f4d6c-162">**QuickInfos für den Tastaturzugriff**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-162">**ToolTips on keyboard access**</span></span>

<span data-ttu-id="f4d6c-163">In Anwendungen, die auf .NET Framework 4.7.2 und frühere Versionen abzielen, kann ein Steuerelement [tooltip](xref:System.Windows.Forms.ToolTip) nur durch Bewegen eines Mauszeigers in das Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-163">In applications that target .NET Framework 4.7.2 and earlier versions, a control [tooltip](xref:System.Windows.Forms.ToolTip) can only be triggered to pop up by moving a mouse pointer into the control.</span></span> <span data-ttu-id="f4d6c-164">Ab .NET Framework 4.8 kann ein Tastaturbenutzer die QuickInfo eines Steuerelements aufrufen, indem das Steuerelement mit einer Tabulatortaste oder Pfeiltasten mit oder ohne Zusatztasten fokussiert wird.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-164">Starting with .NET Framework 4.8, a keyboard user can trigger a control's tooltip by focusing the control using a Tab key or arrow keys with or without modifier keys.</span></span> <span data-ttu-id="f4d6c-165">Für diese Verbesserungen der Barrierefreiheit ist ein zusätzlicher [AppContext-Schalter](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-165">This particular accessibility enhancement requires an additional [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="f4d6c-166">Die folgende Abbildung zeigt die QuickInfo, wenn der Benutzer eine Schaltfläche mit der Tastatur ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-166">The following figure shows the tooltip when the user has selected a button with the keyboard.</span></span>

![Screenshot der QuickInfo, wenn Benutzer mit der Tastatur zur Schaltfläche navigiert.](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f4d6c-168">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-168">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f4d6c-169">Ab .NET Framework 4.8 enthält WPF eine Reihe von Verbesserungen der Barrierefreiheit.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-169">Starting with .NET Framework 4.8, WPF includes a number of accessibility improvements.</span></span>

<span data-ttu-id="f4d6c-170">**Die Sprachausgabe kündigt keine Elemente mit der Sichtbarkeit „Collapsed“ oder „Hidden“ mehr an**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-170">**Screen narrators no longer announce elements with Collapsed or Hidden visibility**</span></span>

<span data-ttu-id="f4d6c-171">Elemente mit der Sichtbarkeit „Collapsed“ oder „Hidden“ werden von der Sprachausgabe nicht mehr angekündigt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-171">Elements with collapsed or hidden visibility are no longer announced by screen reader.</span></span> <span data-ttu-id="f4d6c-172">Benutzeroberflächen, die Elemente mit einer Sichtbarkeit <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> oder <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> enthalten, können durch die Sprachausgabe falsch interpretiert werden, wenn sie dem Benutzer angekündigt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-172">User interfaces that contain elements with a Visibility of <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> or <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> can be misrepresented by screen readers if they are announced to the user.</span></span> <span data-ttu-id="f4d6c-173">Ab .NET Framework 4.8 enthält WPF keine komprimierten oder ausgeblendeten Elemente mehr in der Steuerelementansicht der UIAutomation-Struktur, sodass die Sprachausgabe diese Elemente nicht mehr ankündigen kann.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-173">Starting with .NET Framework 4.8, WPF no longer includes collapsed or hidden elements in the Control View of the UIAutomation tree, so the screen readers can no longer announce these elements.</span></span>

<span data-ttu-id="f4d6c-174">**SelectionTextBrush-Eigenschaft für die Verwendung mit einer nicht Adorner-basierten Textauswahl**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-174">**SelectionTextBrush property for use with non-Adorner based text selection**</span></span>

<span data-ttu-id="f4d6c-175">In .NET Framework 4.7.2 wurde in WPF die Option hinzugefügt, eine <xref:System.Windows.Controls.TextBox>- und <xref:System.Windows.Controls.PasswordBox>-Textauswahl zu zeichnen, ohne die Adorner-Ebene zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-175">In .NET Framework 4.7.2, WPF added the ability to draw <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox> text selection without using the Adorner layer.</span></span> <span data-ttu-id="f4d6c-176">Die Vordergrundfarbe des markierten Texts in diesem Szenario wurde von <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType> vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-176">The foreground color of the selected text in this scenario was dictated by <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="f4d6c-177">.NET Framework 4.8 fügt eine neue Eigenschaft, `SelectionTextBrush`, hinzu, die es Entwicklern ermöglicht, den spezifischen Pinsel für den ausgewählten Text auszuwählen, wenn sie eine nicht Adorner-basierte Textauswahl verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-177">.NET Framework 4.8 adds a new property, `SelectionTextBrush`, that allows developers to select the specific brush for the selected text when using non-Adorner based text selection.</span></span> <span data-ttu-id="f4d6c-178">Diese Eigenschaft funktioniert nur bei <xref:System.Windows.Controls.Primitives.TextBoxBase>-basierten Steuerelementen und dem <xref:System.Windows.Controls.PasswordBox>-Steuerelement in WPF-Anwendungen, bei denen die nicht auf Adorner basierende Textauswahl aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-178">This property works only on <xref:System.Windows.Controls.Primitives.TextBoxBase>-derived controls and the <xref:System.Windows.Controls.PasswordBox> control in WPF applications with non-Adorner-based text selection enabled.</span></span> <span data-ttu-id="f4d6c-179">Sie funktioniert nicht für das <xref:System.Windows.Controls.RichTextBox>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-179">It does not work on the <xref:System.Windows.Controls.RichTextBox> control.</span></span> <span data-ttu-id="f4d6c-180">Wenn die nicht auf Adorner basierende Textauswahl nicht aktiviert ist, wird diese Eigenschaft ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-180">If non-Adorner-based text selection is not enabled, this property is ignored.</span></span>

<span data-ttu-id="f4d6c-181">Um diese Eigenschaft zu verwenden, fügen Sie sie einfach zu Ihrem XAML-Code hinzu, und verwenden Sie den entsprechenden Pinsel oder die passende Bindung.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-181">To use this property, simply add it to your XAML code and use the appropriate brush or binding.</span></span> <span data-ttu-id="f4d6c-182">Die sich daraus ergebende Textauswahl sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-182">The resulting text selection looks like this:</span></span>

![Screenshot der ausgeführten App mit den ausgewählten Wörtern „Hello World“.](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

<span data-ttu-id="f4d6c-184">Sie können die Verwendung der Eigenschaften `SelectionBrush` und `SelectionTextBrush` kombinieren, um jede beliebige Hintergrund- und Vordergrundfarbkombination zu generieren, die Sie für zweckmäßig halten.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-184">You can combine the use of the `SelectionBrush` and `SelectionTextBrush` properties to generate any background and foreground color combination that you deem appropriate.</span></span>

<span data-ttu-id="f4d6c-185">**Unterstützung für die UIAutomation ControllerFor-Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-185">**Support for the UIAutomation ControllerFor property**</span></span>

<span data-ttu-id="f4d6c-186">Die `ControllerFor`-Eigenschaft von UIAutomation gibt ein Array von Automatisierungselementen zurück, die von dem Automatisierungselement geändert werden, das diese Eigenschaft unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-186">UIAutomation’s `ControllerFor` property returns an array of automation elements that are manipulated by the automation element that supports this property.</span></span> <span data-ttu-id="f4d6c-187">Diese Eigenschaft wird häufig bei der Vorschlagsuche verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-187">This property is commonly used for Auto-suggest accessibility.</span></span> <span data-ttu-id="f4d6c-188">`ControllerFor` wird verwendet, wenn ein Automatisierungselement ein oder mehrere Segmente der Benutzeroberfläche der Anwendung oder des Desktops beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-188">`ControllerFor` is used when an automation element affects one or more segments of the application UI or the desktop.</span></span> <span data-ttu-id="f4d6c-189">Andernfalls ist es schwierig, die Auswirkungen des Steuerelementvorgangs den Elementen der Benutzeroberfläche zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-189">Otherwise, it is hard to associate the impact of the control operation with UI elements.</span></span> <span data-ttu-id="f4d6c-190">Dieses Feature fügt die Möglichkeit hinzu, dass Steuerelemente einen Wert für die `ControllerFor`-Eigenschaft bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-190">This feature adds the ability for controls to provide a value for the `ControllerFor` property.</span></span>

<span data-ttu-id="f4d6c-191">.NET Framework 4.8 fügt eine neue virtuelle Methode hinzu: <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-191">.NET Framework 4.8 adds a new virtual method, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4d6c-192">Auf einen Wert für die `ControllerFor` Eigenschaft einfach diese Methode überschreiben und Zurückgeben einer `List<AutomationPeer>` für die Steuerelemente, die von diesem bearbeiteten <xref:System.Windows.Automation.Peers.AutomationPeer>:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-192">To provide a value for the `ControllerFor` property, simply override this method and return a `List<AutomationPeer>` for the controls being manipulated by this <xref:System.Windows.Automation.Peers.AutomationPeer>:</span></span>

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

<span data-ttu-id="f4d6c-193">**QuickInfos für den Tastaturzugriff**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-193">**Tooltips on keyboard access**</span></span>

<span data-ttu-id="f4d6c-194">In .NET Framework 4.7.2 und früheren Versionen werden QuickInfos nur angezeigt, wenn der Benutzer den Mauszeiger über ein Steuerelement bewegt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-194">In .NET Framework 4.7.2 and earlier versions, tooltips display only when the user hovers the mouse cursor over a control.</span></span> <span data-ttu-id="f4d6c-195">In .NET Framework 4.8 werden QuickInfos auch beim Fokussieren mit der Tastatur sowie über eine Tastenkombination angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-195">In .NET Framework 4.8, tooltips also display on keyboard focus, as well as via a keyboard shortcut.</span></span>

<span data-ttu-id="f4d6c-196">Um dieses Feature zu aktivieren, muss eine Anwendung .NET Framework 4.8 als Ziel verwenden oder sich mit den `Switch.UseLegacyAccessibilityFeatures.3`- und `Switch.UseLegacyToolTipDisplay`-[AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Optionen anmelden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-196">To enable this feature, an application needs to target .NET Framework 4.8 or opt-in by using the `Switch.UseLegacyAccessibilityFeatures.3` and `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches.</span></span> <span data-ttu-id="f4d6c-197">Nachfolgend finden Sie die Konfigurationsdatei für eine Beispielanwendung:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-197">The following is a sample application configuration file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

<span data-ttu-id="f4d6c-198">Nach der Aktivierung zeigen alle Steuerelemente, die eine QuickInfo enthalten, diese an, sobald die Tastatur auf das Steuerelement fokussiert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-198">Once enabled, all controls that contain a tooltip display it once the control receives keyboard focus.</span></span> <span data-ttu-id="f4d6c-199">Die QuickInfo kann im Laufe der Zeit oder bei einer Änderung des Tastaturfokus deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-199">The tooltip can be dismissed over time or when the keyboard focus changes.</span></span> <span data-ttu-id="f4d6c-200">Benutzer können die QuickInfo auch manuell verwerfen, indem sie eine neue Tastenkombination verwenden, STRG + UMSCHALT + F10.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-200">Users can also dismiss the tooltip manually by using a new keyboard shortcut, Ctrl + Shift + F10.</span></span> <span data-ttu-id="f4d6c-201">Wenn die QuickInfo verworfen wurde, kann sie mithilfe der gleichen Tastenkombination wieder angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-201">Once the tooltip has been dismissed it can be displayed again by using the same keyboard shortcut.</span></span>

> [!NOTE]
> <span data-ttu-id="f4d6c-202">[Menüband-QuickInfos](xref:System.Windows.Controls.Ribbon.RibbonToolTip) auf <xref:System.Windows.Controls.Ribbon.Ribbon>-Steuerelementen werden nicht beim Tastaturfokus angezeigt, sondern nur über die Tastenkombination.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-202">[Ribbon tooltips](xref:System.Windows.Controls.Ribbon.RibbonToolTip) on <xref:System.Windows.Controls.Ribbon.Ribbon> controls won’t show on keyboard focus; they only show via the keyboard shortcut.</span></span>

<span data-ttu-id="f4d6c-203">**Unterstützung für SizeOfSet- und PositionInSet-UIAutomation-Eigenschaften hinzugefügt**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-203">**Added Support for SizeOfSet and PositionInSet UIAutomation properties**</span></span>

<span data-ttu-id="f4d6c-204">Windows 10 hat zwei neue UIAutomation-Eigenschaften eingeführt, `SizeOfSet` und `PositionInSet`, die von Anwendungen verwendet werden, um die Anzahl der Elemente in einem Satz zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-204">Windows 10 introduced two new UIAutomation properties, `SizeOfSet` and `PositionInSet`, which are used by applications to describe the count of items in a set.</span></span> <span data-ttu-id="f4d6c-205">UIAutomation-Clientanwendungen wie die Sprachausgabe können dann eine Anwendung hinsichtlich dieser Eigenschaften abfragen und eine genaue Darstellung der Benutzeroberfläche der Anwendung ankündigen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-205">UIAutomation client applications such as screen readers can then query an application for these properties and announce an accurate representation of the application’s UI.</span></span>

<span data-ttu-id="f4d6c-206">Ab .NET Framework 4.8 stellt WPF diese beiden Eigenschaften für UIAutomation in WPF-Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-206">Starting with .NET Framework 4.8, WPF  exposes these two properties to UIAutomation in WPF applications.</span></span> <span data-ttu-id="f4d6c-207">Dafür stehen zwei Methoden zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-207">This can be accomplished in two ways:</span></span>

- <span data-ttu-id="f4d6c-208">Verwenden von Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="f4d6c-208">By using dependency properties.</span></span>

  <span data-ttu-id="f4d6c-209">WPF fügt zwei neue Abhängigkeitseigenschaften, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> und <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>, hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-209">WPF adds two new dependency properties, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4d6c-210">Ein Entwickler kann diese Werte mit XAML festlegen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-210">A developer can use XAML to set their values:</span></span>

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- <span data-ttu-id="f4d6c-211">Überschreiben von virtuellen AutomationPeer-Methoden</span><span class="sxs-lookup"><span data-stu-id="f4d6c-211">By overriding AutomationPeer virtual methods.</span></span>

  <span data-ttu-id="f4d6c-212">Die AutomationPeer-Klasse wurde mit den virtuellen Methoden <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> und <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> erweitert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-212">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> and <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> virtual methods been added to the AutomationPeer class.</span></span> <span data-ttu-id="f4d6c-213">Ein Entwickler kann diese Werte für `SizeOfSet` und `PositionInSet` durch Überschreiben dieser Methode bereitstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-213">A developer can provide values for `SizeOfSet` and `PositionInSet` by overriding these methods, as shown in the following example:</span></span>

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

<span data-ttu-id="f4d6c-214">Darüber hinaus stellen Elemente in <xref:System.Windows.Controls.ItemsControl>-Instanzen automatisch einen Wert für diese Eigenschaften ohne zusätzliche Maßnahmen des Entwicklers bereit.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-214">In addition, items in <xref:System.Windows.Controls.ItemsControl> instances provide a value for these properties automatically without additional action from the developer.</span></span> <span data-ttu-id="f4d6c-215">Wenn ein <xref:System.Windows.Controls.ItemsControl> gruppiert ist, wird die Sammlung von Gruppen als Satz dargestellt, und jede Gruppe wird als separater Satz gezählt. Dabei gibt jedes Element innerhalb dieser Gruppe seine Position innerhalb dieser Gruppe sowie die Größe der Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-215">If an <xref:System.Windows.Controls.ItemsControl> is grouped, the collection of groups is represented as a set, and each group is counted as a separate set, with each item inside that group providing its position inside that group as well as the size of the group.</span></span> <span data-ttu-id="f4d6c-216">Automatische Werte werden durch Virtualisierung nicht beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-216">Automatic values are not affected by virtualization.</span></span> <span data-ttu-id="f4d6c-217">Selbst wenn ein Element nicht realisiert wird, wird es dennoch auf die Gesamtgröße des Satzes angerechnet und beeinflusst die Position im Satz seiner gleichgeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-217">Even if an item is not realized, it is still counted toward the total size of the set and affects the position in the set of its sibling items.</span></span>

<span data-ttu-id="f4d6c-218">Automatische Werte werden nur bereitgestellt, wenn die Anwendung auf .NET Framework 4.8 abzielt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-218">Automatic values are only provided if the application targets .NET Framework 4.8.</span></span> <span data-ttu-id="f4d6c-219">Für Anwendungen, die auf eine frühere Version von .NET-Frameworks abzielen, können Sie die `Switch.UseLegacyAccessibilityFeatures.3`-[AppContext-Option](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) einrichten, wie in der folgenden App.config-Datei gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-219">For applications that target an earlier version of the .NET Framework, you can set the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), as shown in the following App.config file:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="f4d6c-220">Workflow-Designer von Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-220">Windows Workflow Foundation (WF) workflow designer</span></span>

<span data-ttu-id="f4d6c-221">Der Workflow-Designer umfasst in .NET Framework 4.8 folgende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-221">The workflow designer includes the following changes in .NET Framework 4.8:</span></span>

- <span data-ttu-id="f4d6c-222">Benutzer, die die Sprachausgabe verwenden, werden Verbesserungen bei FlowSwitch-case-Bezeichnungen feststellen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-222">Users using Narrator will see improvements in FlowSwitch case labels.</span></span>

- <span data-ttu-id="f4d6c-223">Benutzer, die die Sprachausgabe verwenden, werden Verbesserungen bei Schaltflächenbeschreibungen feststellen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-223">Users using Narrator will see improvements in button descriptions.</span></span>

- <span data-ttu-id="f4d6c-224">Benutzer, die Designs mit hohem Kontrast verwenden, werden Verbesserungen in der Sichtbarkeit des Workflow-Designers und dessen Steuerelementen feststellen. Dazu zählen verbesserte Kontrastverhältnisse zwischen Elementen und leichter erkennbare Auswahlfelder für Fokuselemente.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-224">Users who choose High Contrast themes will see improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

<span data-ttu-id="f4d6c-225">Wenn Ihre Anwendung auf .NET Framework 4.7.2 oder eine frühere Version abzielt, können Sie diese Änderungen übernehmen, indem Sie die `Switch.UseLegacyAccessibilityFeatures.3`-[AppContext-Option](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) in Ihrer Anwendungskonfigurationsdatei auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-225">If your application targets .NET Framework 4.7.2 or an earlier version, you can opt into these changes by setting the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to `false` in your application configuration file.</span></span> <span data-ttu-id="f4d6c-226">Weitere Informationen finden Sie im Abschnitt [Profitieren von Barrierefreiheitsverbesserungen](#taking-advantage-of-accessibility-enhancements) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-226">For more information, see the [Taking advantage of accessibility enhancements](#taking-advantage-of-accessibility-enhancements) section in this article.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-472"></a><span data-ttu-id="f4d6c-227">Neuerungen der Barrierefreiheit in .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="f4d6c-227">What's new in accessibility in .NET Framework 4.7.2</span></span>

<span data-ttu-id="f4d6c-228">.NET Framework 4.7.2 enthält neue Barrierefreiheitsfunktionen für die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-228">.NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="f4d6c-229">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4d6c-229">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="f4d6c-230">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-230">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="f4d6c-231">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4d6c-231">Windows Forms</span></span>

<span data-ttu-id="f4d6c-232">**Vom Betriebssystem definierte Farben in Designs mit hohem Kontrast**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-232">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="f4d6c-233">Ab .NET Framework 4.7.2 verwendet Windows Forms vom Betriebssystem definierte Farben in Designs mit hohem Kontrast.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-233">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="f4d6c-234">Dies hat Auswirkungen auf die folgenden Steuerelemente:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-234">This affects the following controls:</span></span>

- <span data-ttu-id="f4d6c-235">Den Dropdownpfeil des <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="f4d6c-235">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="f4d6c-236">Die Steuerelemente <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> und <xref:System.Windows.Forms.CheckBox>, wenn <xref:System.Windows.Forms.ButtonBase.FlatStyle> auf <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> oder <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-236">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4d6c-237">Zuvor gab es keinen Kontrast zwischen ausgewähltem Text und Hintergrundfarbe, wodurch der Text schwer lesbar war.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-237">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="f4d6c-238">Steuerelemente, die in einem <xref:System.Windows.Forms.GroupBox>-Objekt enthalten sind, dessen <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft auf `false` festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="f4d6c-238">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="f4d6c-239">Die <xref:System.Windows.Forms.ToolStripButton>-, <xref:System.Windows.Forms.ToolStripComboBox>- und <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelemente weisen ein höheres Helligkeitskontrastverhältnis im Modus „Hoher Kontrast“ auf.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-239">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="f4d6c-240">Die <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor>-Eigenschaft von <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-240">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="f4d6c-241">**Verbesserungen der Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-241">**Narrator improvements**</span></span>

<span data-ttu-id="f4d6c-242">Ab .NET Framework 4.7.2 treten die folgenden Verbesserungen der Unterstützung der Sprachausgabe in Kraft:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-242">Starting with .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="f4d6c-243">Sie kündigt jetzt den Wert der <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType>-Eigenschaft an, wenn sie den Text eines <xref:System.Windows.Forms.ToolStripMenuItem> ankündigt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-243">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="f4d6c-244">Sie gibt jetzt an, wenn die <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft von <xref:System.Windows.Forms.ToolStripMenuItem> auf `false` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-244">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="f4d6c-245">Sie stellt jetzt Feedback zum Zustand eines Kontrollkästchens bereit, wenn die <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-245">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="f4d6c-246">Die Fokusreihenfolge des Scanmodus der Sprachausgabe ist mit der visuellen Reihenfolge der Steuerelemente für das ClickOnce-Downloaddialogfenster konsistent.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-246">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="f4d6c-247">**DataGridView-Verbesserungen**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-247">**DataGridView improvements**</span></span>

<span data-ttu-id="f4d6c-248">Ab .NET Framework 4.7.2 wurden mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement die folgenden Barrierefreiheitsverbesserungen eingeführt:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-248">Starting with .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="f4d6c-249">Zeilen können jetzt mithilfe der Tastatur sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-249">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="f4d6c-250">Ein Benutzer kann die F3-TASTE verwenden, um anhand der aktuellen Spalte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-250">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="f4d6c-251">Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> festgelegt ist, ändert sich die Farbe der Spaltenüberschrift, um die aktuelle Spalte anzugeben, wenn der Benutzer mit der TABULATORTASTE die Zellen in der aktuellen Zeile durchläuft.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-251">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="f4d6c-252">Die <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType>-Elements gibt jetzt das richtige übergeordnete Steuerelement zurück.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-252">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="f4d6c-253">**Verbesserte visuelle Hinweise**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-253">**Improved visual cues**</span></span>

- <span data-ttu-id="f4d6c-254">Die <xref:System.Windows.Forms.RadioButton>- und <xref:System.Windows.Forms.CheckBox>-Steuerelemente mit einer leeren <xref:System.Windows.Forms.ButtonBase.Text>-Eigenschaft zeigen einen Fokusindikator an, wenn sie den Fokus erhalten.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-254">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="f4d6c-255">**Verbesserte Unterstützung für das Eigenschaftenraster**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-255">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="f4d6c-256">Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben jetzt nur dann `true` für die <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-256">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="f4d6c-257">Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben nur dann `false` für die <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element vom Benutzer geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-257">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="f4d6c-258">**Verbesserte Tastaturnavigation**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-258">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="f4d6c-259">Das <xref:System.Windows.Forms.ToolStripButton>-Steuerelement lässt den Fokus zu, wenn das Element in einem <xref:System.Windows.Forms.ToolStripPanel>-Element enthalten ist, für das die <xref:System.Windows.Forms.ToolStripPanel.TabStop>-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-259">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f4d6c-260">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-260">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f4d6c-261">**Änderungen an den Steuerelementen CheckBox und RadioButton**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-261">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="f4d6c-262">In .NET Framework 4.7.1 und früheren Versionen weisen die WPF-Steuerelemente <xref:System.Windows.Controls.CheckBox?displayProperty=nameWithType> und <xref:System.Windows.Controls.RadioButton?displayProperty=nameWithType> inkonsistente und im klassischen Design sowie im Design mit hohem Kontrast falsche visuelle Fokuselemente auf.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-262">In .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWithType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWithType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="f4d6c-263">Diese Probleme treten in Fällen auf, in denen für die Steuerelemente keine Inhalte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-263">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="f4d6c-264">Dadurch kann der Übergang zwischen Designs verwirrend wirken und das visuelle Fokuselement schwer zu erkennen sein.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-264">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="f4d6c-265">In .NET Framework, 4.7.2 sind diese visuellen Elemente jetzt designübergreifend konsistenter und im klassischen Design sowie im Design mit hohem Kontrast leichter zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-265">In .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="f4d6c-266">**WinForms-Steuerelemente, die in einer WPF-Anwendungen gehostet werden**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-266">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="f4d6c-267">In .NET Framework 4.7.1 und früheren Versionen konnten Benutzer für das in einer WPF-Anwendung gehostete Steuerelement nicht die TAB-TASTE verwenden, um die WinForms-Ebene zu verlassen, wenn es sich bei dem ersten Steuerelement auf dieser Ebene um das WPF-Steuerelement <xref:System.Windows.Forms.Integration.ElementHost> handelte.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-267">For WinForms control hosted in a WPF application in .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="f4d6c-268">In .NET Framework 4.7.2 können Benutzer jetzt die WinForms-Ebene über die TAB-TASTE verlassen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-268">In .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="f4d6c-269">Es kann jedoch sein, dass automatisierte Anwendungen, für die der Fokus dauerhaft auf der WinForms-Ebene liegen muss, nicht mehr einwandfrei funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-269">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-471"></a><span data-ttu-id="f4d6c-270">Neuerungen der Barrierefreiheit in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="f4d6c-270">What's new in accessibility in .NET Framework 4.7.1</span></span>

<span data-ttu-id="f4d6c-271">.NET Framework 4.7.1 enthält neue Barrierefreiheitsfunktionen für die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-271">.NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="f4d6c-272">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-272">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="f4d6c-273">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4d6c-273">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="f4d6c-274">ASP.NET-Websteuerelemente</span><span class="sxs-lookup"><span data-stu-id="f4d6c-274">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="f4d6c-275">.NET SDK-Tools</span><span class="sxs-lookup"><span data-stu-id="f4d6c-275">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="f4d6c-276">Workflow-Designer von Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-276">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="f4d6c-277">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-277">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="f4d6c-278">**Verbesserungen der Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-278">**Screen reader improvements**</span></span>

<span data-ttu-id="f4d6c-279">Wenn die Verbesserungen der Barrierefreiheit aktiviert sind, enthält .NET Framework 4.7.1 folgende Verbesserungen, die sich auf die Sprachausgabe auswirken:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-279">If accessibility improvements are enabled, .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="f4d6c-280">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.Expander>-Steuerelemente von der Sprachausgabe als Schaltflächen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-280">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="f4d6c-281">Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als erweiterbare bzw. reduzierbare Gruppen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-281">Starting with .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="f4d6c-282">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.DataGridCell>-Steuerelemente von der Sprachausgabe als „benutzerdefiniert“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-282">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="f4d6c-283">Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als (lokalisierte) Datenrasterzellen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-283">Starting with .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="f4d6c-284">Ab .NET Framework 4.7.1 gibt die Sprachausgabe den Namen einer bearbeitbaren <xref:System.Windows.Controls.ComboBox>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-284">Starting with .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="f4d6c-285">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.PasswordBox>-Steuerelemente als „Es befindet sich kein Element in der Ansicht.“ ausgegeben oder wiesen andere fehlerhafte Verhaltensweisen auf.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-285">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="f4d6c-286">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-286">This issue is fixed starting with .NET Framework 4.7.1.</span></span>

<span data-ttu-id="f4d6c-287">**Unterstützung von dynamischen Bereichen für die UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-287">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="f4d6c-288">Die Sprachausgabe unterstützt die Benutzer beim Lesen der Inhalte der Benutzeroberfläche einer Anwendung. Dies geschieht üblicherweise durch eine Sprachausgabe des Texts der Inhalte der Benutzeroberfläche, die den Fokus besitzen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-288">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="f4d6c-289">Wenn ein Element der Benutzeroberfläche sich jedoch verändert oder den Fokus nicht besitzt, wird der Benutzer möglicherweise nicht benachrichtigt, wodurch ihm wichtige Informationen entgehen können.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-289">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="f4d6c-290">Durch dynamische Bereiche soll dieses Problem behoben werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-290">Live regions aim at solving this problem.</span></span> <span data-ttu-id="f4d6c-291">Entwickler können diese verwenden, um der Sprachausgabe oder einem anderen UIAutomation-Client mitzuteilen, dass eine wichtige Änderung an einem Element der Benutzeroberfläche vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-291">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="f4d6c-292">Die Sprachausgabe kann dann entscheiden, wie und wann der Benutzer über diese Änderung informiert wird.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-292">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="f4d6c-293">Folgende APIs wurden zu WPF hinzugefügt, um dynamische Bereiche zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-293">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="f4d6c-294">Die <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>-Felder, die die **LiveSetting**-Eigenschaft und das **LiveRegionChanged**-Ereignis identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-294">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="f4d6c-295">Diese können mithilfe von XAML festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-295">They can be set by using XAML.</span></span>

- <span data-ttu-id="f4d6c-296">Die angefügte Eigenschaft **AutomationProperties.LiveSetting**, die der Sprachausgabe die Wichtigkeit der Änderung der Benutzeroberfläche für den Benutzer mitteilt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-296">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="f4d6c-297">Die <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>-Eigenschaft, die die angefügte Eigenschaft **AutomationProperties.LiveSetting** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-297">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="f4d6c-298">Die <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>-Methode, die überschrieben werden kann, um einen **LiveSetting**-Wert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-298">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="f4d6c-299">Die <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>-Methoden, die einen **LiveSetting**-Wert abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-299">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="f4d6c-300">Die <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>-Enumeration, die die folgenden möglichen **LiveSetting**-Werte definiert:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-300">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

  - <span data-ttu-id="f4d6c-301"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-301"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4d6c-302">Das Element sendet keine Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-302">The element does not send notifications if the content of the live region has changed.</span></span>
  - <span data-ttu-id="f4d6c-303"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-303"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4d6c-304">Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-304">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

  - <span data-ttu-id="f4d6c-305"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-305"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4d6c-306">Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-306">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="f4d6c-307">Sie können einen dynamischen Bereich erstellen, indem Sie die Eigenschaft **AutomationProperties.LiveSetting** wie im folgenden Beispiel dargestellt auf das relevante Element festlegen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-307">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="f4d6c-308">Wenn die Daten im dynamischen Bereich geändert werden und diese Änderung der Sprachausgabe mitgeteilt werden soll, müssen Sie wie im folgenden Beispiel dargestellt explizit ein Ereignis auslösen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-308">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="f4d6c-309">**Hoher Kontrast**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-309">**High contrast**</span></span>

<span data-ttu-id="f4d6c-310">Ab .NET Framework 4.7.1 wurden Verbesserungen am Design „Hoher Kontrast“ für verschiedene WPF-Steuerelemente vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-310">Starting with .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="f4d6c-311">Diese sind nun sichtbar, wenn das <xref:System.Windows.SystemParameters.HighContrast%2A>-Design festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-311">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="f4d6c-312">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-312">These include:</span></span>

- <span data-ttu-id="f4d6c-313"><xref:System.Windows.Controls.Expander>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f4d6c-313"><xref:System.Windows.Controls.Expander> control</span></span>

  <span data-ttu-id="f4d6c-314">Das visuelle Fokuselement für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-314">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="f4d6c-315">Das visuelle Tastaturelement für die <xref:System.Windows.Controls.ComboBox>-, <xref:System.Windows.Controls.ListBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-315">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="f4d6c-316">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-316">For example:</span></span>

  <span data-ttu-id="f4d6c-317">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-317">Before:</span></span>

  ![Screenshot des Expander-Steuerelements mit Fokus und ohne visuelles Fokuselement.](./media/whats-new-in-accessibility/expander-control-before.png)

  <span data-ttu-id="f4d6c-319">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-319">After:</span></span>

  ![Screenshot des Expander-Steuerelements, bei dem der Fokus eine gepunktete Linie um den Text des Steuerelements zeigt.](./media/whats-new-in-accessibility/expander-control-after.png)

- <span data-ttu-id="f4d6c-321"><xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="f4d6c-321"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

  <span data-ttu-id="f4d6c-322">Der Text in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen ist nun leichter zu erkennen, wenn das Design mit hohem Kontrast ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-322">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="f4d6c-323">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-323">For example:</span></span>

  <span data-ttu-id="f4d6c-324">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-324">Before:</span></span>

  ![Screenshot der Optionsschaltflächen und der Kontrollkästchen mit schlechter Lesbarkeit des Texts bei Designs mit hohem Kontrast.](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  <span data-ttu-id="f4d6c-326">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-326">After:</span></span>

  ![Screenshot der Optionsschaltflächen und der Kontrollkästchen mit besserer Lesbarkeit des Texts bei Designs mit hohem Kontrast.](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- <span data-ttu-id="f4d6c-328"><xref:System.Windows.Controls.ComboBox>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f4d6c-328"><xref:System.Windows.Controls.ComboBox> control</span></span>

  <span data-ttu-id="f4d6c-329">Ab .NET Framework 4.7.1 hat der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Steuerelements die gleiche Farbe wie der deaktivierte Text.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-329">Starting with .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="f4d6c-330">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-330">For example:</span></span>

  <span data-ttu-id="f4d6c-331">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-331">Before:</span></span>

  ![Screenshot einer deaktivierten ComboBox, bei der Rahmen und Steuerelementtext unterschiedliche Farben aufweisen.](./media/whats-new-in-accessibility/combo-disabled-before.png)

  <span data-ttu-id="f4d6c-333">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-333">After:</span></span>

  ![Screenshot einer deaktivierten ComboBox, bei der Rahmen und Steuerelementtext dieselbe Farbe aufweisen.](./media/whats-new-in-accessibility/combo-disabled-after.png)

  <span data-ttu-id="f4d6c-335">Darüber hinaus verwenden deaktivierte Schaltflächen und Schaltflächen mit Fokus das richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-335">In addition, disabled and focused buttons use the correct theme color.</span></span>

  <span data-ttu-id="f4d6c-336">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-336">Before:</span></span>

  ![Screenshot einer schwarzen Schaltfläche mit grauem Text „Focus Me“.](./media/whats-new-in-accessibility/button-theme-colors-before.png)

  <span data-ttu-id="f4d6c-338">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-338">After:</span></span>

  ![Screenshot einer blauen Schaltfläche mit schwarzem Text „Focus Me“.](./media/whats-new-in-accessibility/button-theme-colors-after.png)

  <span data-ttu-id="f4d6c-340">In .NET Framework 4.7 und früher führte das Festlegen des Formats eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf `Toolbar.ComboBoxStyleKey` dazu, dass der Dropdownpfeil nicht angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-340">Finally, in .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="f4d6c-341">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-341">This issue is fixed starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="f4d6c-342">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-342">For example:</span></span>

  <span data-ttu-id="f4d6c-343">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-343">Before:</span></span>

  ![Screenshot eines ComboBox-Steuerelements mit nicht sichtbarem Dropdownpfeil.](./media/whats-new-in-accessibility/combo-box-style-key-before.png)

  <span data-ttu-id="f4d6c-345">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-345">After:</span></span>

  ![Screenshot eines ComboBox-Steuerelements mit sichtbarem Dropdownpfeil.](./media/whats-new-in-accessibility/combo-box-style-key-after.png)

- <span data-ttu-id="f4d6c-347"><xref:System.Windows.Controls.DataGrid>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f4d6c-347"><xref:System.Windows.Controls.DataGrid> control</span></span>

  <span data-ttu-id="f4d6c-348">Ab .NET Framework 4.7.1 verwendet der Pfeil für die Sortieranzeige in den <xref:System.Windows.Controls.DataGrid>-Steuerelementen das richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-348">Starting with .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="f4d6c-349">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-349">For example:</span></span>

  <span data-ttu-id="f4d6c-350">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-350">Before:</span></span>

  ![Screenshot des Pfeils für die Sortieranzeige vor der Verbesserung.](./media/whats-new-in-accessibility/sort-indicator-before.png)

  <span data-ttu-id="f4d6c-352">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-352">After:</span></span>

  ![Screenshot des Pfeils für die Sortieranzeige nach der Verbesserung.](./media/whats-new-in-accessibility/sort-indicator-after.png)

  <span data-ttu-id="f4d6c-354">Darüber hinaus wurde in .NET Framework 4.7 und früher das Standarddesign für Links geändert, wodurch Links beim Bewegen der Maus über diese im Modus mit hohem Kontrast in der falschen Farbe angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-354">In addition, in .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="f4d6c-355">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-355">This is resolved starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="f4d6c-356">Auf ähnliche Weise verwenden die Spalten des Kontrollkästchens <xref:System.Windows.Controls.DataGrid> ab .NET Framework 4.7.1 die erwarteten Farben für das Feedback des Tastaturfokus.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-356">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with .NET Framework 4.7.1.</span></span>

  <span data-ttu-id="f4d6c-357">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-357">Before:</span></span>

  ![Screenshot eines Links mit dem Text „Click Me!“](./media/whats-new-in-accessibility/default-link-style-before.png)

  <span data-ttu-id="f4d6c-360">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-360">After:</span></span>

  ![Screenshot eines Links mit dem Text „Click Me!“](./media/whats-new-in-accessibility/default-link-style-after.png)

<span data-ttu-id="f4d6c-363">Weitere Informationen zu Verbesserungen der WPF-Barrierefreiheit in .NET Framework 4.7.1 finden Sie unter [Verbesserung der Barrierefreiheit in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="f4d6c-363">For more information on WPF accessibility improvements in .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="f4d6c-364">Verbesserung der Barrierefreiheit von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4d6c-364">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="f4d6c-365">In .NET Framework 4.7.1 enthält Windows Forms (WinForms) Verbesserungen der Barrierefreiheit für folgende Bereiche:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-365">In .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="f4d6c-366">**Verbesserte Anzeige im Modus mit hohem Kontrast**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-366">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="f4d6c-367">Ab .NET Framework 4.7.1 bieten viele WinForms-Steuerelemente ein verbessertes Rendering für die Modi mit hohem Kontrast, die im Betriebssystem verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-367">Starting with .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="f4d6c-368">In Windows 10 wurden die Werte für einige Systemfarbe im Design mit hohem Kontrast geändert, und Windows Forms basiert auf dem Win32-Framework von Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-368">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="f4d6c-369">Führen Sie für die besten Ergebnisse die aktuelle Version von Windows aus, und aktivieren Sie die neuesten Änderungen am Betriebssystem, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus der supportedOS-Zeile für Windows 10 entfernen, sodass diese folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-369">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

<span data-ttu-id="f4d6c-370">Folgende Änderungen wurden am Design mit hohem Kontrast vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-370">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="f4d6c-371">Die Kontrollkästchen der <xref:System.Windows.Forms.MenuStrip>-Elemente können einfacher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-371">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="f4d6c-372">Wenn diese aktiviert werden, können deaktivierte <xref:System.Windows.Forms.MenuStrip>-Elemente einfacher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-372">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="f4d6c-373">Der Text in einem ausgewählten <xref:System.Windows.Forms.Button>-Kontrollkästchen bildet einen Kontrast zur Auswahlfarbe.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-373">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="f4d6c-374">Deaktivierter Text ist einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-374">Disabled text is easier to read.</span></span> <span data-ttu-id="f4d6c-375">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-375">For example:</span></span>

  <span data-ttu-id="f4d6c-376">Vorher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-376">Before:</span></span>

  ![Screenshot einer APP, die verschiedene im Modus für hohe Kontraste ausgeführte Steuerelemente verwendet, vor den Verbesserungen für die Barrierefreiheit.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png)

  <span data-ttu-id="f4d6c-378">Nachher:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-378">After:</span></span>

  ![Screenshot einer APP, die verschiedene im Modus für hohe Kontraste ausgeführte Steuerelemente verwendet, nach den Verbesserungen für die Barrierefreiheit.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png)

- <span data-ttu-id="f4d6c-380">Verbesserungen am Design mit hohem Kontrast im Dialogfeld der Threadausnahme.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-380">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="f4d6c-381">**Verbesserte Unterstützung für die Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-381">**Improved Narrator support**</span></span>

<span data-ttu-id="f4d6c-382">Windows Forms in .NET Framework 4.7.1 enthält folgende Verbesserungen für die Barrierefreiheit der Sprachausgabe:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-382">Windows Forms in .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="f4d6c-383">Auf das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann über die Sprachausgabe sowie über andere Tools zur Automatisierung der Benutzeroberfläche zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-383">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="f4d6c-384">Das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement teilt der Sprachausgabe mit, wenn der Aktivierungszustand eines Elements geändert wurde, sodass der Benutzer darüber benachrichtigt wird, dass der Wert eines Listenelements verändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-384">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="f4d6c-385">Das <xref:System.Windows.Forms.DataGridViewCell>-Steuerelement teilt der Sprachausgabe den richtigen schreibgeschützten Status mit.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-385">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="f4d6c-386">Die Sprachausgabe kann nun deaktivierten <xref:System.Windows.Forms.ToolStripMenuItem>-Text ausgeben, während deaktivierte Menüelemente zuvor übersprungen wurden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-386">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="f4d6c-387">**Verbesserte Unterstützung für die Barrierefreiheitsmuster der UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-387">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="f4d6c-388">Ab .NET Framework 4.7.1 können die Entwickler von Tools für Barrierefreiheitstechnologien allgemeine API-Barrierefreiheitsmuster und -eigenschaften für mehrere WinForms-Steuerelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-388">Starting with .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="f4d6c-389">Folgende Verbesserungen der Barrierefreiheit wurden vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-389">These accessibility improvements include:</span></span>

- <span data-ttu-id="f4d6c-390">Die <xref:System.Windows.Forms.ComboBox>- und <xref:System.Windows.Forms.ToolStripSplitButton>-Steuerelemente unterstützen nun das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f4d6c-390">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="f4d6c-391">Das <xref:System.Windows.Forms.DataGridViewCheckBoxCell>-Steuerelement unterstützt nun das [Umschaltmuster](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f4d6c-391">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="f4d6c-392">Das <xref:System.Windows.Forms.ToolStripItem>-Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft und das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f4d6c-392">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="f4d6c-393">Die <xref:System.Windows.Forms.NumericUpDown>- und <xref:System.Windows.Forms.DomainUpDown>-Steuerelemente unterstützen die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-393">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="f4d6c-394">**Verbesserter Eigenschaftenbrowser**</span><span class="sxs-lookup"><span data-stu-id="f4d6c-394">**Improved property browser experience**</span></span>

<span data-ttu-id="f4d6c-395">Ab .NET Framework 4.7.1 enthält Windows Forms Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-395">Starting with .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="f4d6c-396">Eine verbesserte Tastaturnavigation durch die verschiedenen Fenster der Dropdownauswahl</span><span class="sxs-lookup"><span data-stu-id="f4d6c-396">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="f4d6c-397">Eine Verringerung unnötiger Tabstopps</span><span class="sxs-lookup"><span data-stu-id="f4d6c-397">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="f4d6c-398">Eine verbesserte Berichterstellung der Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="f4d6c-398">Better reporting of control types.</span></span>
- <span data-ttu-id="f4d6c-399">Ein verbessertes Verhalten der Sprachausgabe</span><span class="sxs-lookup"><span data-stu-id="f4d6c-399">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="f4d6c-400">ASP.NET-Websteuerelemente</span><span class="sxs-lookup"><span data-stu-id="f4d6c-400">ASP.NET web controls</span></span>

<span data-ttu-id="f4d6c-401">Ab .NET Framework 4.7.1 und Visual Studio 2017 Version 15.3 arbeiten ASP.NET-Websteuerelemente effizienter mit den Funktionen für die Barrierefreiheit in Visual Studio zusammen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-401">Starting with .NET Framework 4.7.1 and Visual Studio 2017 version 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="f4d6c-402">Dazu gehören folgende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-402">Changes include the following:</span></span>

- <span data-ttu-id="f4d6c-403">Änderungen, durch die fehlende Barrierefreiheitsmuster für Steuerelemente der Benutzeroberfläche implementiert werden. Zu diesen Steuerelementen zählen z.B. das Dialogfeld **Feld hinzufügen** im **Detailansicht-Assistenten** oder das Dialogfeld **ListView konfigurieren** im **ListView**-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-403">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="f4d6c-404">Änderungen zur Verbesserung der Anzeige im Modus für hohe Kontraste, z.B. beim **DataPager-Feld-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-404">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="f4d6c-405">Änderungen zur Verbesserung der Benutzerfreundlichkeit bei der Tastaturnavigation für Steuerelemente, z.B. beim Dialogfeld **Felder** im Assistenten für das **Bearbeiten von Pagerfeldern** des DataPager-Steuerelements, beim Dialogfeld **ObjectContext konfigurieren** oder beim Dialogfeld **Datenauswahl konfigurieren** des Assistenten zum **Konfigurieren der Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-405">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="f4d6c-406">.NET SDK-Tools</span><span class="sxs-lookup"><span data-stu-id="f4d6c-406">.NET SDK Tools</span></span>

<span data-ttu-id="f4d6c-407">Das [Configuration Editor-Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) und das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) wurden verbessert, indem verschiedene Barrierefreiheitsprobleme verbessert wurden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-407">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="f4d6c-408">In den meisten Fälle handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-408">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="f4d6c-409">Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-409">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="f4d6c-410">Durch diese Verbesserungen ändert sich vorheriges Verhalten wie die Reihenfolge des Tastaturfokus.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-410">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="f4d6c-411">Workflow-Designer von Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-411">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="f4d6c-412">Die Barrierefreiheitsänderungen im Workflow-Designer umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-412">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="f4d6c-413">Die Aktivierreihenfolge wurde bei manchen Steuerelementen in „Von links nach rechts“ und in „Von oben nach unten“ geändert:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-413">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="f4d6c-414">Das Fenster „Korrelation initialisieren“ für das Festlegen von Korrelationsdaten für die <xref:System.ServiceModel.Activities.InitializeCorrelation>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4d6c-414">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="f4d6c-415">Das Fenster „Inhaltsdefinition“ für die Aktivitäten <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply></span><span class="sxs-lookup"><span data-stu-id="f4d6c-415">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="f4d6c-416">Weitere Funktionen sind über die Tastatur verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-416">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="f4d6c-417">Beim Bearbeiten der Eigenschaften einer Aktivität können die Eigenschaftengruppen über die Tastatur reduziert werden, wenn diese zum ersten Mal fokussiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-417">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="f4d6c-418">Auf Warnsymbole kann über die Tastatur zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-418">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="f4d6c-419">Auf die Schaltfläche **Weitere Eigenschaften** im Fenster **Eigenschaften** kann über die Tastatur zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-419">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="f4d6c-420">Tastaturbenutzer können auf die Headerelemente in den Bereichen **Argumente** und **Variablen** des Workflow-Designers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-420">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="f4d6c-421">Verbesserte Sichtbarkeit von Elementen mit Fokus, z.B. in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-421">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="f4d6c-422">Hinzufügen von Zeilen zu Datenrastern, die vom Workflow-Designer und von Aktivitäts-Designern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="f4d6c-422">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="f4d6c-423">Wechseln von Feldern mit der TAB-TASTE in den Aktivitäten <xref:System.ServiceModel.Activities.ReceiveReply> und <xref:System.ServiceModel.Activities.SendReply></span><span class="sxs-lookup"><span data-stu-id="f4d6c-423">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="f4d6c-424">Festlegen von Standardwerten für Variablen oder Argumente</span><span class="sxs-lookup"><span data-stu-id="f4d6c-424">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="f4d6c-425">Sprachausgaben können Folgendes nun richtig erkennen:</span><span class="sxs-lookup"><span data-stu-id="f4d6c-425">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="f4d6c-426">Breakpoints, die im Workflow-Designer festgelegt wurden</span><span class="sxs-lookup"><span data-stu-id="f4d6c-426">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="f4d6c-427">Die Aktivitäten <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> und <xref:System.ServiceModel.Activities.CorrelationScope></span><span class="sxs-lookup"><span data-stu-id="f4d6c-427">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="f4d6c-428">Die Inhalte der <xref:System.ServiceModel.Activities.Receive>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4d6c-428">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="f4d6c-429">Den Zieltyp für die <xref:System.Activities.Statements.InvokeMethod>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4d6c-429">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="f4d6c-430">Das Kombinationsfeld „Ausnahme“ und den Abschnitt „Finally“ in der <xref:System.Activities.Statements.TryCatch>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4d6c-430">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="f4d6c-431">Das Kombinationsfeld „Nachrichtentyp“, den Splitter im Fenster „Korrelationsinitialisierer hinzufügen“, das Fenster „Inhaltsdefinition“ und das Definitionsfenster „CorrelatesOn“ in den Messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-431">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="f4d6c-432">Übertragungen von Zustandsautomaten und Übertragungsziele</span><span class="sxs-lookup"><span data-stu-id="f4d6c-432">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="f4d6c-433">Anmerkungen und Connectors von <xref:System.Activities.Statements.FlowDecision>-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="f4d6c-433">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="f4d6c-434">Die per Rechtsklick aufrufbaren Kontextmenüs von Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="f4d6c-434">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="f4d6c-435">Die Editors für Eigenschaftswerte, die Schaltfläche, „Suche löschen“, die Sortierschaltflächen „Nach Kategorie“ und „Alphabetisch“ sowie das Dialogfeld „Ausdrucks-Editor“ im Eigenschaftenraster</span><span class="sxs-lookup"><span data-stu-id="f4d6c-435">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="f4d6c-436">Den Zoomprozentwert im Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="f4d6c-436">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="f4d6c-437">Das Trennzeichen in den Aktivitäten <xref:System.Activities.Statements.Parallel> und <xref:System.Activities.Statements.Pick></span><span class="sxs-lookup"><span data-stu-id="f4d6c-437">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="f4d6c-438">Die <xref:System.Activities.Statements.InvokeDelegate>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="f4d6c-438">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="f4d6c-439">Das Fenster „Typen auswählen“ für Wörterbuchaktivitäten (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` usw.)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-439">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="f4d6c-440">Das Fenster „.NET-Typ suchen und auswählen“</span><span class="sxs-lookup"><span data-stu-id="f4d6c-440">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="f4d6c-441">Breadcrumbs im Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="f4d6c-441">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="f4d6c-442">Benutzer, die Designs mit hohem Kontrast verwenden, werden viele Verbesserungen in der Sichtbarkeit des Workflow-Designers und dessen Steuerelementen feststellen. Dazu zählen verbesserte Kontrastverhältnisse zwischen Elementen und leichter erkennbare Auswahlfelder für Fokuselemente.</span><span class="sxs-lookup"><span data-stu-id="f4d6c-442">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4d6c-443">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4d6c-443">See also</span></span>

- [<span data-ttu-id="f4d6c-444">What's new in the .NET Framework (Neuerungen in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="f4d6c-444">What's new in the .NET Framework</span></span>](index.md)
