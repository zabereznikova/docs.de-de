---
title: Breaking Changes bei Windows Forms
description: Hier werden die Breaking Changes in Windows Forms für .NET Core und .NET 5 aufgelistet.
ms.date: 09/08/2020
ms.openlocfilehash: c3d2d23601d6a2d9d44761c4371fe34d3d5ed1f3
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656336"
---
# <a name="breaking-changes-in-windows-forms"></a>Breaking Changes bei Windows Forms

Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt. In diesem Artikel werden Breaking Changes für Windows Forms anhand der .NET-Version aufgeführt, in der sie eingeführt wurden. Wenn Sie ein Upgrade einer Windows Forms-App von .NET Framework oder einer früheren Version von .NET Core (3.0 oder höher) durchführen, bietet Ihnen dieser Artikel Unterstützung.

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [Mit DataGridView verbundene APIs lösen jetzt InvalidOperationException aus](#datagridview-related-apis-now-throw-invalidoperationexception) | 5.0 |
| [WinForms- und WPF-Apps verwenden Microsoft.NET.Sdk](#winforms-and-wpf-apps-use-microsoftnetsdk) | 5.0 |
| [Statusleisten-Steuerelement wurde entfernt](#removed-status-bar-controls) | 5.0 |
| [WinForms-Methoden lösen jetzt ArgumentException aus](#winforms-methods-now-throw-argumentexception) | 5.0 |
| [WinForms-Methoden lösen jetzt ArgumentNullException aus](#winforms-methods-now-throw-argumentnullexception) | 5.0 |
| [WinForms-Eigenschaften lösen nun ArgumentOutOfRangeException aus](#winforms-properties-now-throw-argumentoutofrangeexception) | 5.0 |
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

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

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

## <a name="see-also"></a>Siehe auch

- [Portieren einer Windows Forms-App zu .NET Core](../porting/winforms.md)
