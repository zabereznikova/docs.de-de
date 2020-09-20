---
title: 'Breaking Changes: .NET Framework zu .NET Core'
titleSuffix: ''
description: Hier werden die Breaking Changes von .NET Framework zu .NET Core 1.0 bis 3.1 aufgeführt.
ms.date: 05/05/2020
ms.openlocfilehash: 5904a359813b6d07bd2a27d882ade4395efe3256
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656365"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>Breaking Changes für die Migration von .NET Framework zu .NET Core

Wenn Sie eine App von .NET Framework zu den .NET Core-Versionen 1.0 bis 3.1 migrieren, können sich die in diesem Artikel aufgeführten Breaking Changes auf Ihre App auswirken. Breaking Changes werden nach Kategorie angeordnet. Innerhalb einer Kategorie sind sie wiederum nach der .NET Core-Version sortiert, in der sie eingeführt wurden.

> [!NOTE]
> Dieser Artikel enthält keine vollständige Liste mit Breaking Changes zwischen .NET Framework und .NET Core. Die wichtigsten Breaking Changes werden hier hinzugefügt, sobald wir sie kennen.

## <a name="core-net-libraries"></a>Core .NET-Bibliotheken

- [Änderung des Standardwerts von UseShellExecute](#change-in-default-value-of-useshellexecute)
- [UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt](#handling-corrupted-state-exceptions-is-not-supported)
- [UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt](#uribuilder-properties-no-longer-prepend-leading-characters)
- [Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a>Kryptografie

- [Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a>MSBuild

- [Änderung des Manifestdateinamens der Ressource](#resource-manifest-file-name-change)

### <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a>Netzwerk

- [WebClient.CancelAsync wird nicht immer sofort abgebrochen](#webclientcancelasync-doesnt-always-cancel-immediately)

### <a name="net-core-20"></a>.NET Core 2.0

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

## <a name="windows-forms"></a>Windows Forms

Windows Forms-Unterstützung wurde zu .NET Core in Version 3.0 hinzugefügt. Wenn Sie eine Windows Forms-App von .NET Framework zu .NET Core migrieren, können sich die in diesem Artikel aufgeführten Breaking Changes auf Ihre App auswirken.

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

### <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a>Siehe auch

- [APIs, die in .NET Core immer Ausnahmen auslösen](unsupported-apis.md)
- [.NET Framework-Technologien, die für .NET Core nicht verfügbar sind](../porting/net-framework-tech-unavailable.md)
