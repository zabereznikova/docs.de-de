---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in der Basisklassenbibliothek .NET CoreFx auf.
ms.date: 09/20/2019
ms.openlocfilehash: 56a3cf4f4c00a79752d5a98bb086bb9f8c0614b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147574"
---
# <a name="corefx-breaking-changes"></a>Breaking Changes bei CoreFx

CoreFx stellt die von .NET Core verwendeten Primitiven und andere allgemeine Typen bereit.

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | :-: |
| [APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion](#apis-that-report-version-now-report-product-and-not-file-version) | 3.0 |
| [Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | 3.0 |
| [Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten](#floating-point-formatting-and-parsing-behavior-changed) | 3.0 |
| [Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | 3.0 |
| [InvalidAsynchronousStateException wurde in andere Assembly verschoben](#invalidasynchronousstateexception-moved-to-another-assembly) | 3.0 |
| [.NET Core 3.0 befolgt bewährte Unicodemethoden beim Ersetzen von falsch formatierten UTF-8-Bytesequenzen](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences) | 3.0 |
| [TypeDescriptionProviderAttribute wurde in andere Assembly verschoben](#typedescriptionproviderattribute-moved-to-another-assembly) | 3.0 |
| [ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | 3.0 |
| [JSON-Serialisierungsausnahmetyp wurde von JsonException in NotSupportedException geändert](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | 3.0 |
| [Änderung der Semantik von (string)null in Utf8JsonWriter](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | 3.0 |
| [JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | 3.0 |
| [Änderung der JsonFactoryConverter.CreateConverter-Signatur](#jsonfactoryconvertercreateconverter-signature-changed) | 3.0 |
| [Änderungen der JsonElement-API](#jsonelement-api-changes) | 3.0 |
| [FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | 3.0 |
| [Private Felder, die integrierten Strukturtypen hinzugefügt werden](#private-fields-added-to-built-in-struct-types) | 2.1 |
| [Änderung des Standardwerts von UseShellExecute](#change-in-default-value-of-useshellexecute) | 2.1 |
| [OpenSSL-Versionen unter macOS](#openssl-versions-on-macos) | 2.1 |
| [UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | 1.0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***
