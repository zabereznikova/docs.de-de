---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 09/20/2019
ms.openlocfilehash: a2eb4be89d78f50d201272f3449374bc27d8c785
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859928"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="e7168-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="e7168-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="e7168-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="e7168-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="e7168-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="e7168-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e7168-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="e7168-106">Breaking change</span></span> | <span data-ttu-id="e7168-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e7168-107">Version introduced</span></span> |
| - | :-: |
| <span data-ttu-id="e7168-108">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="e7168-108">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="e7168-109">5.0</span><span class="sxs-lookup"><span data-stu-id="e7168-109">5.0</span></span> |
| [<span data-ttu-id="e7168-110">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="e7168-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="e7168-111">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-111">3.0</span></span> |
| [<span data-ttu-id="e7168-112">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="e7168-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="e7168-113">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-113">3.0</span></span> |
| [<span data-ttu-id="e7168-114">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="e7168-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="e7168-115">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-115">3.0</span></span> |
| [<span data-ttu-id="e7168-116">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="e7168-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="e7168-117">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-117">3.0</span></span> |
| [<span data-ttu-id="e7168-118">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="e7168-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="e7168-119">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-119">3.0</span></span> |
| [<span data-ttu-id="e7168-120">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="e7168-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="e7168-121">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-121">3.0</span></span> |
| [<span data-ttu-id="e7168-122">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="e7168-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="e7168-123">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-123">3.0</span></span> |
| [<span data-ttu-id="e7168-124">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="e7168-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="e7168-125">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-125">3.0</span></span> |
| [<span data-ttu-id="e7168-126">JSON-Serialisierungsausnahmetyp wurde von JsonException in NotSupportedException geändert</span><span class="sxs-lookup"><span data-stu-id="e7168-126">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="e7168-127">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-127">3.0</span></span> |
| [<span data-ttu-id="e7168-128">Änderung der Semantik von (string)null in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="e7168-128">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="e7168-129">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-129">3.0</span></span> |
| [<span data-ttu-id="e7168-130">JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf</span><span class="sxs-lookup"><span data-stu-id="e7168-130">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="e7168-131">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-131">3.0</span></span> |
| [<span data-ttu-id="e7168-132">Änderung der JsonFactoryConverter.CreateConverter-Signatur</span><span class="sxs-lookup"><span data-stu-id="e7168-132">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="e7168-133">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-133">3.0</span></span> |
| [<span data-ttu-id="e7168-134">Änderungen der JsonElement-API</span><span class="sxs-lookup"><span data-stu-id="e7168-134">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="e7168-135">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-135">3.0</span></span> |
| [<span data-ttu-id="e7168-136">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="e7168-136">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="e7168-137">3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-137">3.0</span></span> |
| [<span data-ttu-id="e7168-138">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="e7168-138">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="e7168-139">2.1</span><span class="sxs-lookup"><span data-stu-id="e7168-139">2.1</span></span> |
| [<span data-ttu-id="e7168-140">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="e7168-140">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="e7168-141">2.1</span><span class="sxs-lookup"><span data-stu-id="e7168-141">2.1</span></span> |
| [<span data-ttu-id="e7168-142">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="e7168-142">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="e7168-143">2.1</span><span class="sxs-lookup"><span data-stu-id="e7168-143">2.1</span></span> |
| [<span data-ttu-id="e7168-144">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="e7168-144">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="e7168-145">1.0</span><span class="sxs-lookup"><span data-stu-id="e7168-145">1.0</span></span> |
| [<span data-ttu-id="e7168-146">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="e7168-146">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="e7168-147">1.0</span><span class="sxs-lookup"><span data-stu-id="e7168-147">1.0</span></span> |
| [<span data-ttu-id="e7168-148">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="e7168-148">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="e7168-149">1.0</span><span class="sxs-lookup"><span data-stu-id="e7168-149">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="e7168-150">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e7168-150">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="e7168-151">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e7168-151">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="e7168-152">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e7168-152">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="e7168-153">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e7168-153">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***
