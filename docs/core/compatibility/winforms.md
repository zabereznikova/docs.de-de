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
# <a name="breaking-changes-in-windows-forms-for-net-core-30-and-31"></a>Breaking Changes in Windows Forms für .NET Core 3.0 und 3.1

Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt. In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET-Version aufgeführt, in der sie eingeführt wurden. Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [Entfernte Steuerelemente](#removed-controls) | 3.1 |
| [CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3.1 |
| [Control.DefaultFont wurde in Segoe UI 9 pt geändert](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [Modernisierung von FolderBrowserDialog](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [SerializableAttribute aus einigen Windows Forms-Typen entfernt](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [Kompatibilitätsoption AllowUpdateChildControlIndexForTabControls wird nicht unterstützt](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption DomainUpDown.UseLegacyScrolling wird nicht unterstützt](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption DoNotLoadLatestRichEditControl wird nicht unterstützt](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption DoNotSupportSelectAllShortcutInMultilineTextBox wird nicht unterstützt](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption DontSupportReentrantFilterMessage wird nicht unterstützt](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption EnableVisualStyleValidation wird nicht unterstützt](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption UseLegacyContextMenuStripSourceControlValue wird nicht unterstützt](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [Kompatibilitätsoption UseLegacyImages wird nicht unterstützt](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

**_

## <a name="net-core-30"></a>.NET Core 3.0

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

_**

## <a name="see-also"></a>Siehe auch

- [Portieren einer Windows Forms-App zu .NET Core](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
