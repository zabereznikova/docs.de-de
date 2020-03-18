---
title: Breaking Changes bei Windows Forms
description: Listet die Breaking Changes bei Windows Forms für .NET Core auf.
ms.date: 01/08/2020
ms.openlocfilehash: 7fba78382d011bc9d489924fa185a44e598c5a76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398010"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="2b3d6-103">Breaking Changes bei Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b3d6-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="2b3d6-104">Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="2b3d6-105">In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET Core-Version aufgeführt, in der sie eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="2b3d6-106">Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="2b3d6-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="2b3d6-107">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="2b3d6-107">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="2b3d6-108">Entfernte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="2b3d6-108">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="2b3d6-109">CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="2b3d6-109">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="2b3d6-110">Control.DefaultFont wurde in Segoe UI 9 pt geändert</span><span class="sxs-lookup"><span data-stu-id="2b3d6-110">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="2b3d6-111">Modernisierung von FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="2b3d6-111">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="2b3d6-112">SerializableAttribute aus einigen Windows Forms-Typen entfernt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-112">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="2b3d6-113">Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-113">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-114">Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-114">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-115">Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-115">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-116">Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-116">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-117">Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-117">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-118">Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-118">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-119">Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-119">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-120">Kompatibilitätsoption UseLegacyImages wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-120">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="2b3d6-121">Zugriffsänderung für AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="2b3d6-121">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="2b3d6-122">Doppelte APIs aus Windows Forms entfernt</span><span class="sxs-lookup"><span data-stu-id="2b3d6-122">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a><span data-ttu-id="2b3d6-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2b3d6-123">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="2b3d6-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2b3d6-124">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2b3d6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b3d6-125">See also</span></span>

- [<span data-ttu-id="2b3d6-126">Portieren einer Windows Forms-App zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="2b3d6-126">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
