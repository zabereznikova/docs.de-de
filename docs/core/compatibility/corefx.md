---
title: Breaking Changes in .NET-Bibliotheken
description: Hier sind die Breaking Changes an den .NET-Kernbibliotheken für die .NET Core-Versionen 1.0 bis 3.0 aufgeführt.
ms.date: 07/27/2020
ms.openlocfilehash: 092ff36a5e07c9e226fe2a67d5e7cfd391e9d16b
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366880"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a>Breaking Changes in .NET-Bibliotheken für .NET Core 1.0 bis 3.0

Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [Das Übergeben von GroupCollection an IEnumerable\<T> akzeptierende Erweiterungsmethoden erfordert Vermeidung von Mehrdeutigkeit](#passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation) | 3.0 |
| [APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion](#apis-that-report-version-now-report-product-and-not-file-version) | 3.0 |
| [Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | 3.0 |
| [Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten](#floating-point-formatting-and-parsing-behavior-changed) | 3.0 |
| [Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | 3.0 |
| [InvalidAsynchronousStateException wurde in andere Assembly verschoben](#invalidasynchronousstateexception-moved-to-another-assembly) | 3.0 |
| [Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | 3.0 |
| [TypeDescriptionProviderAttribute wurde in andere Assembly verschoben](#typedescriptionproviderattribute-moved-to-another-assembly) | 3.0 |
| [ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | 3.0 |
| [FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | 3.0 |
| [Private Felder, die integrierten Strukturtypen hinzugefügt werden](#private-fields-added-to-built-in-struct-types) | 2.1 |
| [Änderung des Standardwerts von UseShellExecute](#change-in-default-value-of-useshellexecute) | 2.1 |
| [OpenSSL-Versionen unter macOS](#openssl-versions-on-macos) | 2.1 |
| [UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | 1.0 |
| [Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt](#handling-corrupted-state-exceptions-is-not-supported) | 1.0 |
| [UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt](#uribuilder-properties-no-longer-prepend-leading-characters) | 1.0 |
| [Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | 1.0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE [disambiguate-generic-type-for-groupcollection](../../../includes/core-changes/corefx/3.0/disambiguate-generic-type-for-groupcollection.md)]

***

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

**_

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

_*_

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

_**
