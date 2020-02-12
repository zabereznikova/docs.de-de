---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in der Basisklassenbibliothek .NET CoreFx auf.
ms.date: 09/20/2019
ms.openlocfilehash: 9e8a00abfae8bf8f5301a4879cb5274492a2b6fd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093083"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="60937-103">Breaking Changes bei CoreFx</span><span class="sxs-lookup"><span data-stu-id="60937-103">CoreFx breaking changes</span></span>

<span data-ttu-id="60937-104">CoreFx stellt die von .NET Core verwendeten Primitiven und andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="60937-104">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="60937-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="60937-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="60937-106">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="60937-106">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version)
- [<span data-ttu-id="60937-107">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="60937-107">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively)
- [<span data-ttu-id="60937-108">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="60937-108">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed)
- [<span data-ttu-id="60937-109">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="60937-109">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception)
- [<span data-ttu-id="60937-110">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="60937-110">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly)
- [<span data-ttu-id="60937-111">.NET Core 3.0 befolgt bewährte Unicodemethoden beim Ersetzen von falsch formatierten UTF-8-Bytesequenzen</span><span class="sxs-lookup"><span data-stu-id="60937-111">NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences</span></span>](#net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences)
- [<span data-ttu-id="60937-112">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="60937-112">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly)
- [<span data-ttu-id="60937-113">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="60937-113">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes)
- [<span data-ttu-id="60937-114">JSON-Serialisierungsausnahmetyp wurde von JsonException in NotSupportedException geändert</span><span class="sxs-lookup"><span data-stu-id="60937-114">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception)
- [<span data-ttu-id="60937-115">Änderung der Semantik von (string)null in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="60937-115">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter)
- [<span data-ttu-id="60937-116">JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf</span><span class="sxs-lookup"><span data-stu-id="60937-116">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument)
- [<span data-ttu-id="60937-117">Änderung der JsonFactoryConverter.CreateConverter-Signatur</span><span class="sxs-lookup"><span data-stu-id="60937-117">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed)
- [<span data-ttu-id="60937-118">Änderungen der JsonElement-API</span><span class="sxs-lookup"><span data-stu-id="60937-118">JsonElement API changes</span></span>](#jsonelement-api-changes)
- [<span data-ttu-id="60937-119">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="60937-119">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types)
- [<span data-ttu-id="60937-120">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="60937-120">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)

## <a name="net-core-30"></a><span data-ttu-id="60937-121">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="60937-121">.NET Core 3.0</span></span>

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

## <a name="net-core-30-preview-9"></a><span data-ttu-id="60937-122">.NET Core 3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="60937-122">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

## <a name="net-core-30-preview-8"></a><span data-ttu-id="60937-123">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="60937-123">.NET Core 3.0 Preview 8</span></span>

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

## <a name="net-core-30-preview-7"></a><span data-ttu-id="60937-124">.NET Core 3.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="60937-124">.NET Core 3.0 Preview 7</span></span>

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="60937-125">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="60937-125">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***
