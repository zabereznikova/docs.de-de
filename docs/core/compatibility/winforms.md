---
title: Breaking Changes bei Windows Forms
description: Listet die Breaking Changes bei Windows Forms für .NET Core auf.
ms.date: 01/08/2020
ms.openlocfilehash: 25c568a8a0092a9c4874419c64c7dcebea4dce9e
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888121"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="3ec63-103">Breaking Changes bei Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ec63-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="3ec63-104">Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3ec63-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="3ec63-105">In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET Core-Version aufgeführt, in der sie eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3ec63-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="3ec63-106">Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="3ec63-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="3ec63-107">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="3ec63-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="3ec63-108">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="3ec63-108">Breaking change</span></span> | <span data-ttu-id="3ec63-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3ec63-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="3ec63-110">WinForms-APIs lösen nun ArgumentNullException aus</span><span class="sxs-lookup"><span data-stu-id="3ec63-110">WinForms APIs now throw ArgumentNullException</span></span>](#winforms-apis-now-throw-argumentnullexception) | <span data-ttu-id="3ec63-111">5.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-111">5.0</span></span> |
| [<span data-ttu-id="3ec63-112">Entfernte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="3ec63-112">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="3ec63-113">3.1</span><span class="sxs-lookup"><span data-stu-id="3ec63-113">3.1</span></span> |
| [<span data-ttu-id="3ec63-114">CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="3ec63-114">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="3ec63-115">3.1</span><span class="sxs-lookup"><span data-stu-id="3ec63-115">3.1</span></span> |
| [<span data-ttu-id="3ec63-116">Control.DefaultFont wurde in Segoe UI 9 pt geändert</span><span class="sxs-lookup"><span data-stu-id="3ec63-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="3ec63-117">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-117">3.0</span></span> |
| [<span data-ttu-id="3ec63-118">Modernisierung von FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="3ec63-118">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="3ec63-119">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-119">3.0</span></span> |
| [<span data-ttu-id="3ec63-120">SerializableAttribute aus einigen Windows Forms-Typen entfernt</span><span class="sxs-lookup"><span data-stu-id="3ec63-120">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="3ec63-121">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-121">3.0</span></span> |
| [<span data-ttu-id="3ec63-122">Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-122">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-123">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-123">3.0</span></span> |
| [<span data-ttu-id="3ec63-124">Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-124">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-125">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-125">3.0</span></span> |
| [<span data-ttu-id="3ec63-126">Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-126">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-127">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-127">3.0</span></span> |
| [<span data-ttu-id="3ec63-128">Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-128">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-129">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-129">3.0</span></span> |
| [<span data-ttu-id="3ec63-130">Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-130">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-131">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-131">3.0</span></span> |
| [<span data-ttu-id="3ec63-132">Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-132">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-133">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-133">3.0</span></span> |
| [<span data-ttu-id="3ec63-134">Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-134">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-135">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-135">3.0</span></span> |
| [<span data-ttu-id="3ec63-136">Kompatibilitätsoption UseLegacyImages wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3ec63-136">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="3ec63-137">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-137">3.0</span></span> |
| [<span data-ttu-id="3ec63-138">Zugriffsänderung für AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="3ec63-138">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="3ec63-139">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-139">3.0</span></span> |
| [<span data-ttu-id="3ec63-140">Doppelte APIs aus Windows Forms entfernt</span><span class="sxs-lookup"><span data-stu-id="3ec63-140">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="3ec63-141">3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-141">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="3ec63-142">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-142">.NET 5.0</span></span>

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="3ec63-143">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="3ec63-143">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="3ec63-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3ec63-144">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="3ec63-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ec63-145">See also</span></span>

- [<span data-ttu-id="3ec63-146">Portieren einer Windows Forms-App zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="3ec63-146">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
