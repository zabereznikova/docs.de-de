---
title: Breaking Changes bei Windows Forms
description: Liste der Breaking Changes in Windows Forms für .NET Core 3.0 und 3.1
ms.date: 09/08/2020
ms.openlocfilehash: b944f7eea89b61f41feb8eef99e949c2d6017960
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726430"
---
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a><span data-ttu-id="a44e0-103">Breaking Changes in Windows Forms für .NET Core 3.0 und 3.1</span><span class="sxs-lookup"><span data-stu-id="a44e0-103">Breaking changes in Windows Forms for .NET Core 3.0 and 3.1</span></span>

<span data-ttu-id="a44e0-104">Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a44e0-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="a44e0-105">In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET-Version aufgeführt, in der sie eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="a44e0-105">This article lists breaking changes for Windows Forms by the .NET version in which they were introduced.</span></span> <span data-ttu-id="a44e0-106">Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="a44e0-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="a44e0-107">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="a44e0-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a44e0-108">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="a44e0-108">Breaking change</span></span> | <span data-ttu-id="a44e0-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a44e0-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a44e0-110">Entfernte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a44e0-110">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="a44e0-111">3.1</span><span class="sxs-lookup"><span data-stu-id="a44e0-111">3.1</span></span> |
| [<span data-ttu-id="a44e0-112">CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="a44e0-112">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="a44e0-113">3.1</span><span class="sxs-lookup"><span data-stu-id="a44e0-113">3.1</span></span> |
| [<span data-ttu-id="a44e0-114">Control.DefaultFont wurde in Segoe UI 9 pt geändert</span><span class="sxs-lookup"><span data-stu-id="a44e0-114">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="a44e0-115">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-115">3.0</span></span> |
| [<span data-ttu-id="a44e0-116">Modernisierung von FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="a44e0-116">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="a44e0-117">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-117">3.0</span></span> |
| [<span data-ttu-id="a44e0-118">SerializableAttribute aus einigen Windows Forms-Typen entfernt</span><span class="sxs-lookup"><span data-stu-id="a44e0-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="a44e0-119">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-119">3.0</span></span> |
| [<span data-ttu-id="a44e0-120">Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-120">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-121">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-121">3.0</span></span> |
| [<span data-ttu-id="a44e0-122">Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-122">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-123">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-123">3.0</span></span> |
| [<span data-ttu-id="a44e0-124">Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-124">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-125">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-125">3.0</span></span> |
| [<span data-ttu-id="a44e0-126">Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-126">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-127">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-127">3.0</span></span> |
| [<span data-ttu-id="a44e0-128">Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-128">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-129">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-129">3.0</span></span> |
| [<span data-ttu-id="a44e0-130">Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-130">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-131">3.0</span></span> |
| [<span data-ttu-id="a44e0-132">Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-132">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-133">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-133">3.0</span></span> |
| [<span data-ttu-id="a44e0-134">Kompatibilitätsoption UseLegacyImages wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a44e0-134">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="a44e0-135">3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-135">3.0</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="a44e0-136">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a44e0-136">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

<span data-ttu-id="a44e0-137">\*\*_</span><span class="sxs-lookup"><span data-stu-id="a44e0-137">\*\*_</span></span>

## <a name="net-core-30"></a><span data-ttu-id="a44e0-138">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a44e0-138">.NET Core 3.0</span></span>

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

<span data-ttu-id="a44e0-139">_\*\*</span><span class="sxs-lookup"><span data-stu-id="a44e0-139">_\*\*</span></span>

## <a name="see-also"></a><span data-ttu-id="a44e0-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a44e0-140">See also</span></span>

- [<span data-ttu-id="a44e0-141">Portieren einer Windows Forms-App zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="a44e0-141">Port a Windows Forms app to .NET Core</span></span>](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
