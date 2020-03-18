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
# <a name="breaking-changes-in-windows-forms"></a>Breaking Changes bei Windows Forms

Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt. In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET Core-Version aufgeführt, in der sie eingeführt wurden. Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

- [Entfernte Steuerelemente](#removed-controls)
- [CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [Control.DefaultFont wurde in Segoe UI 9 pt geändert](#default-control-font-changed-to-segoe-ui-9-pt)
- [Modernisierung von FolderBrowserDialog](#modernization-of-the-folderbrowserdialog)
- [SerializableAttribute aus einigen Windows Forms-Typen entfernt](#serializableattribute-removed-from-some-windows-forms-types)
- [Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [Kompatibilitätsoption UseLegacyImages wird nicht unterstützt](#uselegacyimages-compatibility-switch-not-supported)
- [Zugriffsänderung für AccessibleObject.RuntimeIDFirstItem](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [Doppelte APIs aus Windows Forms entfernt](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="see-also"></a>Weitere Informationen

- [Portieren einer Windows Forms-App zu .NET Core](../porting/winforms.md)
