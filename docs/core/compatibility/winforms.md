---
title: Breaking Changes bei Windows Forms
description: Hier werden die Breaking Changes in Windows Forms für .NET Core und .NET 5 aufgelistet.
ms.date: 09/08/2020
ms.openlocfilehash: 01810a690227bbcab2103f00767315dbc5d5fae3
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400643"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="32825-103">Breaking Changes bei Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32825-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="32825-104">Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="32825-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="32825-105">In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET-Version aufgeführt, in der sie eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="32825-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="32825-106">Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="32825-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="32825-107">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="32825-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="32825-108">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="32825-108">Breaking change</span></span> | <span data-ttu-id="32825-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="32825-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="32825-110">TextFormatFlags.ModifyString ist veraltet</span><span class="sxs-lookup"><span data-stu-id="32825-110">TextFormatFlags.ModifyString is obsolete</span></span>](#textformatflagsmodifystring-is-obsolete) | <span data-ttu-id="32825-111">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-111">5.0</span></span> |
| [<span data-ttu-id="32825-112">DataGridView setzt Schriftarten für angepasste Zelltypen nicht mehr zurück</span><span class="sxs-lookup"><span data-stu-id="32825-112">DataGridView no longer resets fonts for customized cell styles</span></span>](#datagridview-no-longer-resets-fonts-for-customized-cell-styles) | <span data-ttu-id="32825-113">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-113">5.0</span></span> |
| [<span data-ttu-id="32825-114">Das OutputType-Atttribut für WPF- und WinForms-Apps wurde auf WinExe festgelegt</span><span class="sxs-lookup"><span data-stu-id="32825-114">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="32825-115">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-115">5.0</span></span> |
| [<span data-ttu-id="32825-116">Mit DataGridView verbundene APIs lösen jetzt InvalidOperationException aus</span><span class="sxs-lookup"><span data-stu-id="32825-116">DataGridView-related APIs now throw InvalidOperationException</span></span>](#datagridview-related-apis-now-throw-invalidoperationexception) | <span data-ttu-id="32825-117">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-117">5.0</span></span> |
| [<span data-ttu-id="32825-118">WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="32825-118">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="32825-119">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-119">5.0</span></span> |
| [<span data-ttu-id="32825-120">Statusleisten-Steuerelement wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="32825-120">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="32825-121">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-121">5.0</span></span> |
| [<span data-ttu-id="32825-122">WinForms-Methoden lösen jetzt ArgumentException aus</span><span class="sxs-lookup"><span data-stu-id="32825-122">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="32825-123">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-123">5.0</span></span> |
| [<span data-ttu-id="32825-124">WinForms-Methoden lösen jetzt ArgumentNullException aus</span><span class="sxs-lookup"><span data-stu-id="32825-124">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="32825-125">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-125">5.0</span></span> |
| [<span data-ttu-id="32825-126">WinForms-Eigenschaften lösen nun ArgumentOutOfRangeException aus</span><span class="sxs-lookup"><span data-stu-id="32825-126">WinForms properties now throw ArgumentOutOfRangeException</span></span>](#winforms-properties-now-throw-argumentoutofrangeexception) | <span data-ttu-id="32825-127">5.0</span><span class="sxs-lookup"><span data-stu-id="32825-127">5.0</span></span> |
| [<span data-ttu-id="32825-128">Entfernte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="32825-128">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="32825-129">3.1</span><span class="sxs-lookup"><span data-stu-id="32825-129">3.1</span></span> |
| [<span data-ttu-id="32825-130">CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="32825-130">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="32825-131">3.1</span><span class="sxs-lookup"><span data-stu-id="32825-131">3.1</span></span> |
| [<span data-ttu-id="32825-132">Control.DefaultFont wurde in Segoe UI 9 pt geändert</span><span class="sxs-lookup"><span data-stu-id="32825-132">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="32825-133">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-133">3.0</span></span> |
| [<span data-ttu-id="32825-134">Modernisierung von FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="32825-134">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="32825-135">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-135">3.0</span></span> |
| [<span data-ttu-id="32825-136">SerializableAttribute aus einigen Windows Forms-Typen entfernt</span><span class="sxs-lookup"><span data-stu-id="32825-136">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="32825-137">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-137">3.0</span></span> |
| [<span data-ttu-id="32825-138">Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-138">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="32825-139">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-139">3.0</span></span> |
| [<span data-ttu-id="32825-140">Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-140">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="32825-141">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-141">3.0</span></span> |
| [<span data-ttu-id="32825-142">Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-142">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="32825-143">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-143">3.0</span></span> |
| [<span data-ttu-id="32825-144">Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-144">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="32825-145">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-145">3.0</span></span> |
| [<span data-ttu-id="32825-146">Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-146">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="32825-147">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-147">3.0</span></span> |
| [<span data-ttu-id="32825-148">Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-148">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="32825-149">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-149">3.0</span></span> |
| [<span data-ttu-id="32825-150">Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-150">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="32825-151">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-151">3.0</span></span> |
| [<span data-ttu-id="32825-152">Kompatibilitätsoption UseLegacyImages wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="32825-152">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="32825-153">3.0</span><span class="sxs-lookup"><span data-stu-id="32825-153">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="32825-154">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="32825-154">.NET 5.0</span></span>

[!INCLUDE [modifystring-field-of-textformatflags-obsolete](../../../includes/core-changes/windowsforms/5.0/modifystring-field-of-textformatflags-obsolete.md)]

***

[!INCLUDE [datagridview-doesnt-reset-custom-font-settings](../../../includes/core-changes/windowsforms/5.0/datagridview-doesnt-reset-custom-font-settings.md)]

<span data-ttu-id="32825-155">\*\*_</span><span class="sxs-lookup"><span data-stu-id="32825-155">\*\*_</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

_*_

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

_*_

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

_*_

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

_*_

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

_*_

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

_*_

## <a name="net-core-31"></a><span data-ttu-id="32825-156">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="32825-156">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

_*_

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="32825-157">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="32825-157">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

_*_

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

_*_

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

_*_

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

<span data-ttu-id="32825-158">_\*\*</span><span class="sxs-lookup"><span data-stu-id="32825-158">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="32825-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32825-159">See also</span></span>

- [<span data-ttu-id="32825-160">Portieren einer Windows Forms-App zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="32825-160">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
