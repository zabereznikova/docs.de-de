---
title: Neuerungen der Barrierefreiheit in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bdb1bf5d7e32c2e05eb779eed16c311cbd3eae7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212507"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="2ef2e-102">Neuerungen der Barrierefreiheit in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ef2e-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="2ef2e-103">Die Anwendungen von .NET Framework sollen eine bessere Barrierefreiheit für Ihre Benutzer bieten.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="2ef2e-104">Durch Barrierefreiheitsfunktionen wird es einer Anwendung ermöglicht, den Benutzern von Hilfstechnologien ein angemessenes Erlebnis zu bieten.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="2ef2e-105">Ab .NET Framework 4.7.1 enthält .NET Framework zahlreiche Verbesserungen der Barrierefreiheit, die es den Entwicklern ermöglichen, barrierefreie Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="2ef2e-106">Barrierefreiheitsparameter</span><span class="sxs-lookup"><span data-stu-id="2ef2e-106">Accessibility switches</span></span>

<span data-ttu-id="2ef2e-107">Wenn Ihre App auf .NET Framework 4.7 oder niedriger ausgerichtet ist, aber auf .NET Framework 4.7.1 oder höher ausgeführt wird, können Sie sie für Barrierefreiheitsfeatures konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-107">You can configure your app to opt into accessibility features if it targets the .NET Framework 4.7 or an earlier version but is running on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="2ef2e-108">Sie können auch Ihre App für Legacy-Features konfigurieren (und Barrierefreiheitsfeatures außen vor lassen), wenn diese auf .NET Framework 4.7.1 oder höher ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="2ef2e-109">Jede .NET Framework-Version, die Barrierefreiheitsfeatures umfasst, verfügt über einen versionsspezifischen Barrierefreiheitsparameter, den Sie dem [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt des [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Elements in der Konfigurationsdatei der Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="2ef2e-110">Die folgenden Parameter werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-110">The following are the supported switches:</span></span>

|<span data-ttu-id="2ef2e-111">Version</span><span class="sxs-lookup"><span data-stu-id="2ef2e-111">Version</span></span>|<span data-ttu-id="2ef2e-112">Schalter</span><span class="sxs-lookup"><span data-stu-id="2ef2e-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="2ef2e-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="2ef2e-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="2ef2e-114">„Switch.UseLegacyAccessibilityFeatures“</span><span class="sxs-lookup"><span data-stu-id="2ef2e-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="2ef2e-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="2ef2e-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="2ef2e-116">„Switch.UseLegacyAccessibilityFeatures.2“</span><span class="sxs-lookup"><span data-stu-id="2ef2e-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="2ef2e-117">Profitieren von Barrierefreiheitserweiterungen</span><span class="sxs-lookup"><span data-stu-id="2ef2e-117">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="2ef2e-118">Die neuen Barrierefreiheitsfunktionen werden standardmäßig für Anwendungen aktiviert, die .NET Framework 4.7.1 oder höher anzielen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-118">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="2ef2e-119">Zusätzlich können Anwendungen, die eine frühere Version von .NET Framework anzielen, aber unter .NET Framework 4.7.1 oder höher ausgeführt werden, veraltete Verhaltensweisen für die Barrierefreiheit deaktivieren (und dadurch die Verbesserungen der Barrierefreiheit nutzen), indem Sie dem [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung einen Parameter hinzufügen und deren Wert auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-119">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="2ef2e-120">Das folgende Beispiel zeigt, wie Sie die in .NET Framework 4.7.1 eingeführten Barrierefreiheitserweiterungen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-120">The following shows how to opt in to accessibility enhancements introduced in the .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="2ef2e-121">Wenn Sie die Barrierefreiheitsoptionen in einer höheren Version von .NET Framework aktivieren, müssen Sie ebenfalls die Features früherer Versionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-121">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="2ef2e-122">Sie benötigen das folgende [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element, um Ihre App so zu konfigurieren, dass Sie die Verbesserungen der Barrierefreiheit sowohl in .NET Framework 4.7.1 als auch in Version 4.7.2 nutzen können:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-122">Configuring your app to take advantage of accessibility improvements in both the .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="2ef2e-123">Wiederherstellen von Legacyverhalten</span><span class="sxs-lookup"><span data-stu-id="2ef2e-123">Restoring legacy behavior</span></span>

<span data-ttu-id="2ef2e-124">Anwendungen, die Versionen von .NET Framework ab 4.7.1 anzielen, können die Barrierefreiheitsfeatures deaktivieren, indem folgendes Element zum [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)-Element im [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md)-Abschnitt der Konfigurationsdatei der Anwendung hinzugefügt und deren Wert auf `true` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-124">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="2ef2e-125">Beispielsweise deaktiviert die folgende Konfiguration die Barrierefreiheitsfeatures, die in .NET Framework 4.7.2 eingeführt wurden:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-125">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a><span data-ttu-id="2ef2e-126">Neuerungen der Barrierefreiheit in .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="2ef2e-126">What's new in accessibility in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="2ef2e-127">.NET Framework 4.7.2 enthält neue Barrierefreiheitsfeatures für die folgenden Bereiche:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-127">The .NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="2ef2e-128">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef2e-128">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="2ef2e-129">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-129">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="2ef2e-130">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef2e-130">Windows Forms</span></span>

<span data-ttu-id="2ef2e-131">**Vom Betriebssystem definierte Farben in Designs mit hohem Kontrast**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-131">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="2ef2e-132">Ab .NET Framework 4.7.2 verwendet Windows Forms vom Betriebssystem definierte Farben in Designs mit hohem Kontrast.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-132">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="2ef2e-133">Dies hat Auswirkungen auf die folgenden Steuerelemente:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-133">This affects the following controls:</span></span>

- <span data-ttu-id="2ef2e-134">Den Dropdownpfeil des <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2ef2e-134">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="2ef2e-135">Die Steuerelemente <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> und <xref:System.Windows.Forms.CheckBox>, wenn <xref:System.Windows.Forms.ButtonBase.FlatStyle> auf <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> oder <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-135">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ef2e-136">Zuvor gab es keinen Kontrast zwischen ausgewähltem Text und Hintergrundfarbe, wodurch der Text schwer lesbar war.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-136">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="2ef2e-137">Steuerelemente, die in einem <xref:System.Windows.Forms.GroupBox>-Objekt enthalten sind, dessen <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft auf `false` festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="2ef2e-137">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="2ef2e-138">Die <xref:System.Windows.Forms.ToolStripButton>-, <xref:System.Windows.Forms.ToolStripComboBox>- und <xref:System.Windows.Forms.ToolStripDropDownButton>-Steuerelemente weisen ein höheres Helligkeitskontrastverhältnis im Modus „Hoher Kontrast“ auf.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-138">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="2ef2e-139">Die <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor>-Eigenschaft von <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-139">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="2ef2e-140">**Verbesserungen der Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-140">**Narrator improvements**</span></span>

<span data-ttu-id="2ef2e-141">Ab .NET Framework 4.7.2 treten die folgenden Verbesserungen der Unterstützung der Sprachausgabe in Kraft:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-141">Starting with the .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="2ef2e-142">Sie kündigt jetzt den Wert der <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType>-Eigenschaft an, wenn sie den Text eines <xref:System.Windows.Forms.ToolStripMenuItem> ankündigt.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-142">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="2ef2e-143">Sie gibt jetzt an, wenn die <xref:System.Windows.Forms.Control.Enabled>-Eigenschaft von <xref:System.Windows.Forms.ToolStripMenuItem> auf `false` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-143">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="2ef2e-144">Sie stellt jetzt Feedback zum Zustand eines Kontrollkästchens bereit, wenn die <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType>-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-144">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="2ef2e-145">Die Fokusreihenfolge des Scanmodus der Sprachausgabe ist mit der visuellen Reihenfolge der Steuerelemente für das ClickOnce-Downloaddialogfenster konsistent.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-145">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="2ef2e-146">**DataGridView-Verbesserungen**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-146">**DataGridView improvements**</span></span>

<span data-ttu-id="2ef2e-147">Ab .NET Framework 4.7.2 wurden mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement die folgenden Barrierefreiheitsverbesserungen eingeführt:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-147">Starting with the .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="2ef2e-148">Zeilen können jetzt mithilfe der Tastatur sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-148">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="2ef2e-149">Ein Benutzer kann die F3-TASTE verwenden, um anhand der aktuellen Spalte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-149">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="2ef2e-150">Wenn <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> auf <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> festgelegt ist, ändert sich die Farbe der Spaltenüberschrift, um die aktuelle Spalte anzugeben, wenn der Benutzer mit der TABULATORTASTE die Zellen in der aktuellen Zeile durchläuft.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-150">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="2ef2e-151">Die <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType>-Eigenschaft eines <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType>-Elements gibt jetzt das richtige übergeordnete Steuerelement zurück.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-151">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="2ef2e-152">**Verbesserte visuelle Hinweise**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-152">**Improved visual cues**</span></span>

- <span data-ttu-id="2ef2e-153">Die <xref:System.Windows.Forms.RadioButton>- und <xref:System.Windows.Forms.CheckBox>-Steuerelemente mit einer leeren <xref:System.Windows.Forms.ButtonBase.Text>-Eigenschaft zeigen einen Fokusindikator an, wenn sie den Fokus erhalten.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-153">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="2ef2e-154">**Verbesserte Unterstützung für das Eigenschaftenraster**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-154">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="2ef2e-155">Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben jetzt nur dann `true` für die <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-155">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="2ef2e-156">Die untergeordneten Elemente des <xref:System.Windows.Forms.PropertyGrid>-Steuerelements geben nur dann `false` für die <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>-Eigenschaft zurück, wenn ein PropertyGrid-Element vom Benutzer geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-156">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="2ef2e-157">**Verbesserte Tastaturnavigation**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-157">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="2ef2e-158">Das <xref:System.Windows.Forms.ToolStripButton>-Steuerelement lässt den Fokus zu, wenn das Element in einem <xref:System.Windows.Forms.ToolStripPanel>-Element enthalten ist, für das die <xref:System.Windows.Forms.ToolStripPanel.TabStop>-Eigenschaft auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-158">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="2ef2e-159">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="2ef2e-160">**Änderungen an den Steuerelementen CheckBox und RadioButton**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-160">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="2ef2e-161">In .NET Framework 4.7.1 und früheren Versionen weisen die WPF-Steuerelemente <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> und <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> inkonsistente und im klassischen Design sowie im Design mit hohem Kontrast falsche visuelle Fokuselemente auf.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-161">In the .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="2ef2e-162">Diese Probleme treten in Fällen auf, in denen für die Steuerelemente keine Inhalte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-162">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="2ef2e-163">Dadurch kann der Übergang zwischen Designs verwirrend wirken und das visuelle Fokuselement schwer zu erkennen sein.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-163">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="2ef2e-164">In .NET Framework, 4.7.2 sind diese visuellen Elemente jetzt designübergreifend konsistenter und im klassischen Design sowie im Design mit hohem Kontrast leichter zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-164">In the .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="2ef2e-165">**WinForms-Steuerelemente, die in einer WPF-Anwendungen gehostet werden**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-165">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="2ef2e-166">In .NET Framework 4.7.1 und früheren Versionen konnten Benutzer für das in einer WPF-Anwendung gehostete Steuerelement nicht die TAB-TASTE verwenden, um die WinForms-Ebene zu verlassen, wenn es sich bei dem ersten Steuerelement auf dieser Ebene um das WPF-Steuerelement <xref:System.Windows.Forms.Integration.ElementHost> handelte.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-166">For WinForms control hosted in a WPF application in the .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="2ef2e-167">In .NET Framework 4.7.2 können Benutzer jetzt die WinForms-Ebene über die TAB-TASTE verlassen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-167">In the .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="2ef2e-168">Es kann jedoch sein, dass automatisierte Anwendungen, für die der Fokus dauerhaft auf der WinForms-Ebene liegen muss, nicht mehr einwandfrei funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-168">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="2ef2e-169">Neuerungen der Barrierefreiheit in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="2ef2e-169">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="2ef2e-170">.NET Framework 4.7.1 enthält neue Barrierefreiheitsfunktionen für folgende Bereiche:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-170">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="2ef2e-171">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-171">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="2ef2e-172">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef2e-172">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="2ef2e-173">ASP.NET-Websteuerelemente</span><span class="sxs-lookup"><span data-stu-id="2ef2e-173">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="2ef2e-174">.NET SDK-Tools</span><span class="sxs-lookup"><span data-stu-id="2ef2e-174">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="2ef2e-175">Workflow-Designer von Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-175">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="2ef2e-176">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-176">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="2ef2e-177">**Verbesserungen der Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-177">**Screen reader improvements**</span></span>

<span data-ttu-id="2ef2e-178">Wenn die Verbesserungen der Barrierefreiheit aktiviert sind, enthält .NET Framework 4.7.1 folgende Verbesserungen, die sich auf die Sprachausgabe auswirken:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-178">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="2ef2e-179">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.Expander>-Steuerelemente von der Sprachausgabe als Schaltflächen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-179">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="2ef2e-180">Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als erweiterbare bzw. reduzierbare Gruppen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-180">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="2ef2e-181">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.DataGridCell>-Steuerelemente von der Sprachausgabe als „benutzerdefiniert“ ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-181">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="2ef2e-182">Ab .NET Framework 4.7.1 werden diese ordnungsgemäß als (lokalisierte) Datenrasterzellen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-182">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="2ef2e-183">Ab .NET Framework 4.7.1 gibt die Sprachausgabe den Namen einer bearbeitbaren <xref:System.Windows.Controls.ComboBox>-Klasse aus.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-183">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="2ef2e-184">In .NET Framework 4.7 und früher wurden <xref:System.Windows.Controls.PasswordBox>-Steuerelemente als „Es befindet sich kein Element in der Ansicht.“ ausgegeben oder wiesen andere fehlerhafte Verhaltensweisen auf.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-184">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="2ef2e-185">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-185">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>

<span data-ttu-id="2ef2e-186">**Unterstützung von dynamischen Bereichen für die UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-186">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="2ef2e-187">Die Sprachausgabe unterstützt die Benutzer beim Lesen der Inhalte der Benutzeroberfläche einer Anwendung. Dies geschieht üblicherweise durch eine Sprachausgabe des Texts der Inhalte der Benutzeroberfläche, die den Fokus besitzen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-187">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="2ef2e-188">Wenn ein Element der Benutzeroberfläche sich jedoch verändert oder den Fokus nicht besitzt, wird der Benutzer möglicherweise nicht benachrichtigt, wodurch ihm wichtige Informationen entgehen können.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-188">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="2ef2e-189">Durch dynamische Bereiche soll dieses Problem behoben werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-189">Live regions aim at solving this problem.</span></span> <span data-ttu-id="2ef2e-190">Entwickler können diese verwenden, um der Sprachausgabe oder einem anderen UIAutomation-Client mitzuteilen, dass eine wichtige Änderung an einem Element der Benutzeroberfläche vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-190">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="2ef2e-191">Die Sprachausgabe kann dann entscheiden, wie und wann der Benutzer über diese Änderung informiert wird.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-191">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="2ef2e-192">Folgende APIs wurden zu WPF hinzugefügt, um dynamische Bereiche zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-192">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="2ef2e-193">Die <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>-Felder, die die **LiveSetting**-Eigenschaft und das **LiveRegionChanged**-Ereignis identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-193">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="2ef2e-194">Diese können mithilfe von XAML festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-194">They can be set by using XAML.</span></span>

- <span data-ttu-id="2ef2e-195">Die angefügte Eigenschaft **AutomationProperties.LiveSetting**, die der Sprachausgabe die Wichtigkeit der Änderung der Benutzeroberfläche für den Benutzer mitteilt.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-195">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="2ef2e-196">Die <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>-Eigenschaft, die die angefügte Eigenschaft **AutomationProperties.LiveSetting** identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-196">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="2ef2e-197">Die <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>-Methode, die überschrieben werden kann, um einen **LiveSetting**-Wert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-197">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="2ef2e-198">Die <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType>- und <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>-Methoden, die einen **LiveSetting**-Wert abrufen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-198">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="2ef2e-199">Die <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>-Enumeration, die die folgenden möglichen **LiveSetting**-Werte definiert:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-199">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="2ef2e-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ef2e-201">Das Element sendet keine Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-201">The element does not send notifications if the content of the live region has changed.</span></span>
   - <span data-ttu-id="2ef2e-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ef2e-203">Das Element sendet nicht unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-203">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

   - <span data-ttu-id="2ef2e-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ef2e-205">Das Element sendet unterbrechende Benachrichtigungen, wenn der Inhalt des dynamischen Bereichs geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-205">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="2ef2e-206">Sie können einen dynamischen Bereich erstellen, indem Sie die Eigenschaft **AutomationProperties.LiveSetting** wie im folgenden Beispiel dargestellt auf das relevante Element festlegen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-206">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="2ef2e-207">Wenn die Daten im dynamischen Bereich geändert werden und diese Änderung der Sprachausgabe mitgeteilt werden soll, müssen Sie wie im folgenden Beispiel dargestellt explizit ein Ereignis auslösen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-207">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="2ef2e-208">**Hoher Kontrast**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-208">**High contrast**</span></span>

<span data-ttu-id="2ef2e-209">Ab .NET Framework 4.7.1 wurden Verbesserungen am Design „Hoher Kontrast“ für verschiedene WPF-Steuerelemente vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-209">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="2ef2e-210">Diese sind nun sichtbar, wenn das <xref:System.Windows.SystemParameters.HighContrast%2A>-Design festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-210">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="2ef2e-211">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-211">These include:</span></span>

- <span data-ttu-id="2ef2e-212"><xref:System.Windows.Controls.Expander>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ef2e-212"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="2ef2e-213">Das visuelle Fokuselement für das <xref:System.Windows.Controls.Expander>-Steuerelement wird nun angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-213">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="2ef2e-214">Das visuelle Tastaturelement für die <xref:System.Windows.Controls.ComboBox>-, <xref:System.Windows.Controls.ListBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-214">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="2ef2e-215">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-215">For example:</span></span>

    <span data-ttu-id="2ef2e-216">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-216">Before:</span></span> 

    ![Das Expander-Steuerelement mit Fokus vor der Verbesserung der Barrierefreiheit](media/expander-before.png)

    <span data-ttu-id="2ef2e-218">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-218">After:</span></span> 

    ![Das Expander-Steuerelement mit Fokus nach der Verbesserung der Barrierefreiheit](media/expander-after.png)

- <span data-ttu-id="2ef2e-220"><xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="2ef2e-220"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

    <span data-ttu-id="2ef2e-221">Der Text in den <xref:System.Windows.Controls.CheckBox>- und <xref:System.Windows.Controls.RadioButton>-Steuerelementen ist nun leichter zu erkennen, wenn das Design mit hohem Kontrast ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-221">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="2ef2e-222">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-222">For example:</span></span>

    <span data-ttu-id="2ef2e-223">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-223">Before:</span></span> 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus vor der Verbesserung der Barrierefreiheit](media/radio-button-before.png)

    <span data-ttu-id="2ef2e-225">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-225">After:</span></span> 

    ![Das Optionsfeld im Design mit hohem Kontrast mit Fokus nach der Verbesserung der Barrierefreiheit](media/radio-button-after.png)

- <span data-ttu-id="2ef2e-227"><xref:System.Windows.Controls.ComboBox>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ef2e-227"><xref:System.Windows.Controls.ComboBox> control</span></span>

    <span data-ttu-id="2ef2e-228">Ab .NET Framework 4.7.1 hat der Rahmen eines deaktivierten <xref:System.Windows.Controls.ComboBox>-Steuerelements die gleiche Farbe wie der deaktivierte Text.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-228">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="2ef2e-229">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-229">For example:</span></span>

    <span data-ttu-id="2ef2e-230">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-230">Before:</span></span> 

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements vor der Verbesserung der Barrierefreiheit](media/combo-disabled-before.png)

    <span data-ttu-id="2ef2e-232">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-232">After:</span></span>   

     ![Rahmen und Text eines deaktivierten ComboBox-Steuerelements nach der Verbesserung der Barrierefreiheit](media/combo-disabled-after.png)

    <span data-ttu-id="2ef2e-234">Darüber hinaus verwenden deaktivierte Schaltflächen und Schaltflächen mit Fokus das richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-234">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="2ef2e-235">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-235">Before:</span></span>

    ![Farbdesign der Schaltflächen vor der Verbesserung der Barrierefreiheit](media/button-themes-before.png) 

    <span data-ttu-id="2ef2e-237">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-237">After:</span></span> 

    ![Farbdesign der Schaltflächen nach der Verbesserung der Barrierefreiheit](media/button-themes-after.png) 

    <span data-ttu-id="2ef2e-239">In .NET Framework 4.7 und früher führte das Festlegen des Formats eines <xref:System.Windows.Controls.ComboBox>-Steuerelements auf `Toolbar.ComboBoxStyleKey` dazu, dass der Dropdownpfeil nicht angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-239">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="2ef2e-240">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-240">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="2ef2e-241">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-241">For example:</span></span>

    <span data-ttu-id="2ef2e-242">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-242">Before:</span></span> 

    ![„Toolbar.ComboBoxStyleKey“ vor der Verbesserung der Barrierefreiheit](media/comboboxstylekey-before.png) 

    <span data-ttu-id="2ef2e-244">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-244">After:</span></span> 

    ![„Toolbar.ComboBoxStyleKey“ nach der Verbesserung der Barrierefreiheit](media/comboboxstylekey-after.png) 

- <span data-ttu-id="2ef2e-246"><xref:System.Windows.Controls.DataGrid>-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ef2e-246"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="2ef2e-247">Ab .NET Framework 4.7.1 verwendet der Pfeil für die Sortieranzeige in den <xref:System.Windows.Controls.DataGrid>-Steuerelementen das richtige Farbdesign.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-247">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="2ef2e-248">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-248">For example:</span></span>

    <span data-ttu-id="2ef2e-249">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-249">Before:</span></span> 

    ![Pfeil für die Sortieranzeige vor der Verbesserung der Barrierefreiheit](media/sort-indicator-before.png) 

    <span data-ttu-id="2ef2e-251">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-251">After:</span></span>   

    ![Pfeil für die Sortieranzeige nach der Verbesserung der Barrierefreiheit](media/sort-indicator-after.png) 

    <span data-ttu-id="2ef2e-253">Darüber hinaus wurde in .NET Framework 4.7 und früher das Standarddesign für Links geändert, wodurch Links beim Bewegen der Maus über diese im Modus mit hohem Kontrast in der falschen Farbe angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-253">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="2ef2e-254">Dieses Problem wurde in .NET Framework 4.7.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-254">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="2ef2e-255">Auf ähnliche Weise verwenden die Spalten des Kontrollkästchens <xref:System.Windows.Controls.DataGrid> ab .NET Framework 4.7.1 die erwarteten Farben für das Feedback des Tastaturfokus.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-255">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="2ef2e-256">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-256">Before:</span></span> 

    ![DataGrid-Standarddesign für Links vor der Verbesserung der Barrierefreiheit](media/default-link-style-before.png) 

    <span data-ttu-id="2ef2e-258">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-258">After:</span></span>    

    ![DataGrid-Standarddesign für Links nach der Verbesserung der Barrierefreiheit](media/default-link-style-after.png) 

<span data-ttu-id="2ef2e-260">Weitere Informationen zu Verbesserungen der WPF-Barrierefreiheit in .NET Framework 4.7.1 finden Sie unter [Verbesserung der Barrierefreiheit in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="2ef2e-260">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="2ef2e-261">Verbesserung der Barrierefreiheit von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ef2e-261">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="2ef2e-262">In .NET Framework 4.7.1 enthält Windows Forms (WinForms) Verbesserungen der Barrierefreiheit für folgende Bereiche:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-262">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="2ef2e-263">**Verbesserte Anzeige im Modus mit hohem Kontrast**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-263">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="2ef2e-264">Ab .NET Framework 4.7.1 bieten viele WinForms-Steuerelemente ein verbessertes Rendering für die Modi mit hohem Kontrast, die im Betriebssystem verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-264">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="2ef2e-265">In Windows 10 wurden die Werte für einige Systemfarbe im Design mit hohem Kontrast geändert, und Windows Forms basiert auf dem Win32-Framework von Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-265">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="2ef2e-266">Führen Sie für die besten Ergebnisse die aktuelle Version von Windows aus, und aktivieren Sie die neuesten Änderungen am Betriebssystem, indem Sie eine app.manifest-Datei zu einer Testanwendung hinzufügen und den Kommentar aus der SupportedOS-Zeile für Windows 10 entfernen, sodass diese folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-266">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

<span data-ttu-id="2ef2e-267">Folgende Änderungen wurden am Design mit hohem Kontrast vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-267">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="2ef2e-268">Die Kontrollkästchen der <xref:System.Windows.Forms.MenuStrip>-Elemente können einfacher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-268">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="2ef2e-269">Wenn diese aktiviert werden, können deaktivierte <xref:System.Windows.Forms.MenuStrip>-Elemente einfacher angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-269">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="2ef2e-270">Der Text in einem ausgewählten <xref:System.Windows.Forms.Button>-Kontrollkästchen bildet einen Kontrast zur Auswahlfarbe.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-270">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="2ef2e-271">Deaktivierter Text ist einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-271">Disabled text is easier to read.</span></span> <span data-ttu-id="2ef2e-272">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-272">For example:</span></span>

    <span data-ttu-id="2ef2e-273">Vorher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-273">Before:</span></span>

    ![Deaktivierter Text vor der Verbesserung der Barrierefreiheit](media/wf-disabled-before.png) 

    <span data-ttu-id="2ef2e-275">Nachher:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-275">After:</span></span>

    ![Deaktivierter Text nach der Verbesserung der Barrierefreiheit](media/wf-disabled-after.png) 

- <span data-ttu-id="2ef2e-277">Verbesserungen am Design mit hohem Kontrast im Dialogfeld der Threadausnahme.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-277">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="2ef2e-278">**Verbesserte Unterstützung für die Sprachausgabe**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-278">**Improved Narrator support**</span></span>

<span data-ttu-id="2ef2e-279">Windows Forms in .NET Framework 4.7.1 enthält folgende Verbesserungen für die Barrierefreiheit der Sprachausgabe:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-279">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="2ef2e-280">Auf das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement kann über die Sprachausgabe sowie über andere Tools zur Automatisierung der Benutzeroberfläche zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-280">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="2ef2e-281">Das <xref:System.Windows.Forms.CheckedListBox>-Steuerelement teilt der Sprachausgabe mit, wenn der Aktivierungszustand eines Elements geändert wurde, sodass der Benutzer darüber benachrichtigt wird, dass der Wert eines Listenelements verändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-281">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="2ef2e-282">Das <xref:System.Windows.Forms.DataGridViewCell>-Steuerelement teilt der Sprachausgabe den richtigen schreibgeschützten Status mit.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-282">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="2ef2e-283">Die Sprachausgabe kann nun deaktivierten <xref:System.Windows.Forms.ToolStripMenuItem>-Text ausgeben, während deaktivierte Menüelemente zuvor übersprungen wurden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-283">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="2ef2e-284">**Verbesserte Unterstützung für die Barrierefreiheitsmuster der UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-284">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="2ef2e-285">Ab .NET Framework 4.7.1 können die Entwickler von Tools für Barrierefreiheitstechnologien allgemeine API-Barrierefreiheitsmuster und -eigenschaften für mehrere WinForms-Steuerelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-285">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="2ef2e-286">Folgende Verbesserungen der Barrierefreiheit wurden vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-286">These accessibility improvements include:</span></span>

- <span data-ttu-id="2ef2e-287">Die <xref:System.Windows.Forms.ComboBox>- und <xref:System.Windows.Forms.ToolStripSplitButton>-Steuerelemente unterstützen nun das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2ef2e-287">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="2ef2e-288">Das <xref:System.Windows.Forms.DataGridViewCheckBoxCell>-Steuerelement unterstützt nun das [Umschaltmuster](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2ef2e-288">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="2ef2e-289">Das <xref:System.Windows.Forms.ToolStripItem>-Steuerelement unterstützt die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft und das [Muster für das Erweitern/Reduzieren](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="2ef2e-289">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="2ef2e-290">Die <xref:System.Windows.Forms.NumericUpDown>- und <xref:System.Windows.Forms.DomainUpDown>-Steuerelemente unterstützen die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-290">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="2ef2e-291">**Verbesserter Eigenschaftenbrowser**</span><span class="sxs-lookup"><span data-stu-id="2ef2e-291">**Improved property browser experience**</span></span>

<span data-ttu-id="2ef2e-292">Ab .NET Framework 4.7.1 enthält Windows Forms Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-292">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="2ef2e-293">Eine verbesserte Tastaturnavigation durch die verschiedenen Fenster der Dropdownauswahl</span><span class="sxs-lookup"><span data-stu-id="2ef2e-293">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="2ef2e-294">Eine Verringerung unnötiger Tabstopps</span><span class="sxs-lookup"><span data-stu-id="2ef2e-294">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="2ef2e-295">Eine verbesserte Berichterstellung der Steuerelementtypen</span><span class="sxs-lookup"><span data-stu-id="2ef2e-295">Better reporting of control types.</span></span>
- <span data-ttu-id="2ef2e-296">Ein verbessertes Verhalten der Sprachausgabe</span><span class="sxs-lookup"><span data-stu-id="2ef2e-296">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="2ef2e-297">ASP.NET-Websteuerelemente</span><span class="sxs-lookup"><span data-stu-id="2ef2e-297">ASP.NET web controls</span></span>

<span data-ttu-id="2ef2e-298">Ab .NET Framework 4.7.1 und Visual Studio 2017 15.3 arbeiten .ASP.NET-Websteuerelemente effizienter mit den Funktionen für die Barrierefreiheit in Visual Studio zusammen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-298">Starting with the .NET Framework 4.7.1 and Visual Studio 2017 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="2ef2e-299">Dazu gehören folgende Änderungen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-299">Changes include the following:</span></span>

- <span data-ttu-id="2ef2e-300">Änderungen, durch die fehlende Barrierefreiheitsmuster für Steuerelemente der Benutzeroberfläche implementiert werden. Zu diesen Steuerelementen zählen z.B. das Dialogfeld **Feld hinzufügen** im **Detailansicht-Assistenten** oder das Dialogfeld **ListView konfigurieren** im **ListView**-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-300">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="2ef2e-301">Änderungen zur Verbesserung der Anzeige im Modus für hohe Kontraste, z.B. beim **DataPager-Feld-Editor**.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-301">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="2ef2e-302">Änderungen zur Verbesserung der Benutzerfreundlichkeit bei der Tastaturnavigation für Steuerelemente, z.B. beim Dialogfeld **Felder** im Assistenten für das **Bearbeiten von Pagerfeldern** des DataPager-Steuerelements, beim Dialogfeld **ObjectContext konfigurieren** oder beim Dialogfeld **Datenauswahl konfigurieren** des Assistenten zum **Konfigurieren der Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-302">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="2ef2e-303">.NET SDK-Tools</span><span class="sxs-lookup"><span data-stu-id="2ef2e-303">.NET SDK Tools</span></span>

<span data-ttu-id="2ef2e-304">Das [Configuration Editor-Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) und das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) wurden verbessert, indem verschiedene Barrierefreiheitsprobleme verbessert wurden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-304">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="2ef2e-305">In den meisten Fälle handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-305">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="2ef2e-306">Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-306">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="2ef2e-307">Durch diese Verbesserungen ändert sich vorheriges Verhalten wie die Reihenfolge des Tastaturfokus.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-307">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="2ef2e-308">Workflow-Designer von Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-308">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="2ef2e-309">Die Barrierefreiheitsänderungen im Workflow-Designer umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-309">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="2ef2e-310">Die Aktivierreihenfolge wurde bei manchen Steuerelementen in „Von links nach rechts“ und in „Von oben nach unten“ geändert:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-310">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="2ef2e-311">Das Fenster „Korrelation initialisieren“ für das Festlegen von Korrelationsdaten für die <xref:System.ServiceModel.Activities.InitializeCorrelation>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="2ef2e-311">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="2ef2e-312">Das Fenster „Inhaltsdefinition“ für die Aktivitäten <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply></span><span class="sxs-lookup"><span data-stu-id="2ef2e-312">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="2ef2e-313">Weitere Funktionen sind über die Tastatur verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-313">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="2ef2e-314">Beim Bearbeiten der Eigenschaften einer Aktivität können die Eigenschaftengruppen über die Tastatur reduziert werden, wenn diese zum ersten Mal fokussiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-314">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="2ef2e-315">Auf Warnsymbole kann über die Tastatur zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-315">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="2ef2e-316">Auf die Schaltfläche **Weitere Eigenschaften** im Fenster **Eigenschaften** kann über die Tastatur zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-316">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="2ef2e-317">Tastaturbenutzer können auf die Headerelemente in den Bereichen **Argumente** und **Variablen** des Workflow-Designers zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-317">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="2ef2e-318">Verbesserte Sichtbarkeit von Elementen mit Fokus, z.B. in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-318">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="2ef2e-319">Hinzufügen von Zeilen zu Datenrastern, die vom Workflow-Designer und von Aktivitäts-Designern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="2ef2e-319">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="2ef2e-320">Wechseln von Feldern mit der TAB-TASTE in den Aktivitäten <xref:System.ServiceModel.Activities.ReceiveReply> und <xref:System.ServiceModel.Activities.SendReply></span><span class="sxs-lookup"><span data-stu-id="2ef2e-320">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="2ef2e-321">Festlegen von Standardwerten für Variablen oder Argumente</span><span class="sxs-lookup"><span data-stu-id="2ef2e-321">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="2ef2e-322">Sprachausgaben können Folgendes nun richtig erkennen:</span><span class="sxs-lookup"><span data-stu-id="2ef2e-322">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="2ef2e-323">Breakpoints, die im Workflow-Designer festgelegt wurden</span><span class="sxs-lookup"><span data-stu-id="2ef2e-323">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="2ef2e-324">Die Aktivitäten <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> und <xref:System.ServiceModel.Activities.CorrelationScope></span><span class="sxs-lookup"><span data-stu-id="2ef2e-324">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="2ef2e-325">Die Inhalte der <xref:System.ServiceModel.Activities.Receive>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="2ef2e-325">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="2ef2e-326">Den Zieltyp für die <xref:System.Activities.Statements.InvokeMethod>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="2ef2e-326">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="2ef2e-327">Das Kombinationsfeld „Ausnahme“ und den Abschnitt „Finally“ in der <xref:System.Activities.Statements.TryCatch>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="2ef2e-327">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="2ef2e-328">Das Kombinationsfeld „Nachrichtentyp“, den Splitter im Fenster „Korrelationsinitialisierer hinzufügen“, das Fenster „Inhaltsdefinition“ und das Definitionsfenster „CorrelatesOn“ in den Messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> und <xref:System.ServiceModel.Activities.ReceiveReply>)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-328">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="2ef2e-329">Übertragungen von Zustandsautomaten und Übertragungsziele</span><span class="sxs-lookup"><span data-stu-id="2ef2e-329">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="2ef2e-330">Anmerkungen und Connectors von <xref:System.Activities.Statements.FlowDecision>-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="2ef2e-330">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="2ef2e-331">Die per Rechtsklick aufrufbaren Kontextmenüs von Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="2ef2e-331">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="2ef2e-332">Die Editors für Eigenschaftswerte, die Schaltfläche, „Suche löschen“, die Sortierschaltflächen „Nach Kategorie“ und „Alphabetisch“ sowie das Dialogfeld „Ausdrucks-Editor“ im Eigenschaftenraster</span><span class="sxs-lookup"><span data-stu-id="2ef2e-332">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="2ef2e-333">Den Zoomprozentwert im Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="2ef2e-333">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="2ef2e-334">Das Trennzeichen in den Aktivitäten <xref:System.Activities.Statements.Parallel> und <xref:System.Activities.Statements.Pick></span><span class="sxs-lookup"><span data-stu-id="2ef2e-334">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="2ef2e-335">Die <xref:System.Activities.Statements.InvokeDelegate>-Aktivität</span><span class="sxs-lookup"><span data-stu-id="2ef2e-335">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="2ef2e-336">Das Fenster „Typen auswählen“ für Wörterbuchaktivitäten (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` usw.)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-336">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="2ef2e-337">Das Fenster „.NET-Typ suchen und auswählen“</span><span class="sxs-lookup"><span data-stu-id="2ef2e-337">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="2ef2e-338">Breadcrumbs im Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="2ef2e-338">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="2ef2e-339">Benutzer, die Designs mit hohem Kontrast verwenden, werden viele Verbesserungen in der Sichtbarkeit des Workflow-Designers und dessen Steuerelementen feststellen. Dazu zählen verbesserte Kontrastverhältnisse zwischen Elementen und leichter erkennbare Auswahlfelder für Fokuselemente.</span><span class="sxs-lookup"><span data-stu-id="2ef2e-339">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ef2e-340">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ef2e-340">See also</span></span>

- [<span data-ttu-id="2ef2e-341">What's new in the .NET Framework (Neuerungen in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="2ef2e-341">What's new in the .NET Framework</span></span>](whats-new.md)
