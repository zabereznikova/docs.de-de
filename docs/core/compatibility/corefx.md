---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 09/20/2019
ms.openlocfilehash: 45de0f0d418437cf1677c9a8c7cfc9b6c33a24ef
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144478"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="8862c-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="8862c-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="8862c-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="8862c-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="8862c-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="8862c-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="8862c-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="8862c-106">Breaking change</span></span> | <span data-ttu-id="8862c-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8862c-107">Version introduced</span></span> |
| - | :-: |
| <span data-ttu-id="8862c-108">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="8862c-108">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="8862c-109">5.0</span><span class="sxs-lookup"><span data-stu-id="8862c-109">5.0</span></span> |
| [<span data-ttu-id="8862c-110">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="8862c-110">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="8862c-111">5.0</span><span class="sxs-lookup"><span data-stu-id="8862c-111">5.0</span></span> |
| [<span data-ttu-id="8862c-112">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="8862c-112">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="8862c-113">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-113">3.0</span></span> |
| [<span data-ttu-id="8862c-114">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="8862c-114">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="8862c-115">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-115">3.0</span></span> |
| [<span data-ttu-id="8862c-116">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="8862c-116">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="8862c-117">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-117">3.0</span></span> |
| [<span data-ttu-id="8862c-118">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="8862c-118">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="8862c-119">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-119">3.0</span></span> |
| [<span data-ttu-id="8862c-120">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="8862c-120">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="8862c-121">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-121">3.0</span></span> |
| [<span data-ttu-id="8862c-122">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="8862c-122">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="8862c-123">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-123">3.0</span></span> |
| [<span data-ttu-id="8862c-124">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="8862c-124">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="8862c-125">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-125">3.0</span></span> |
| [<span data-ttu-id="8862c-126">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="8862c-126">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="8862c-127">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-127">3.0</span></span> |
| [<span data-ttu-id="8862c-128">JSON-Serialisierungsausnahmetyp wurde von JsonException in NotSupportedException geändert</span><span class="sxs-lookup"><span data-stu-id="8862c-128">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="8862c-129">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-129">3.0</span></span> |
| [<span data-ttu-id="8862c-130">Änderung der Semantik von (string)null in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="8862c-130">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="8862c-131">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-131">3.0</span></span> |
| [<span data-ttu-id="8862c-132">JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf</span><span class="sxs-lookup"><span data-stu-id="8862c-132">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="8862c-133">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-133">3.0</span></span> |
| [<span data-ttu-id="8862c-134">Änderung der JsonFactoryConverter.CreateConverter-Signatur</span><span class="sxs-lookup"><span data-stu-id="8862c-134">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="8862c-135">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-135">3.0</span></span> |
| [<span data-ttu-id="8862c-136">Änderungen der JsonElement-API</span><span class="sxs-lookup"><span data-stu-id="8862c-136">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="8862c-137">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-137">3.0</span></span> |
| [<span data-ttu-id="8862c-138">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="8862c-138">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="8862c-139">3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-139">3.0</span></span> |
| [<span data-ttu-id="8862c-140">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="8862c-140">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="8862c-141">2.1</span><span class="sxs-lookup"><span data-stu-id="8862c-141">2.1</span></span> |
| [<span data-ttu-id="8862c-142">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="8862c-142">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="8862c-143">2.1</span><span class="sxs-lookup"><span data-stu-id="8862c-143">2.1</span></span> |
| [<span data-ttu-id="8862c-144">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="8862c-144">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="8862c-145">2.1</span><span class="sxs-lookup"><span data-stu-id="8862c-145">2.1</span></span> |
| [<span data-ttu-id="8862c-146">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="8862c-146">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="8862c-147">1.0</span><span class="sxs-lookup"><span data-stu-id="8862c-147">1.0</span></span> |
| [<span data-ttu-id="8862c-148">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="8862c-148">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="8862c-149">1.0</span><span class="sxs-lookup"><span data-stu-id="8862c-149">1.0</span></span> |
| [<span data-ttu-id="8862c-150">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="8862c-150">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="8862c-151">1.0</span><span class="sxs-lookup"><span data-stu-id="8862c-151">1.0</span></span> |
| [<span data-ttu-id="8862c-152">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="8862c-152">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="8862c-153">1.0</span><span class="sxs-lookup"><span data-stu-id="8862c-153">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="8862c-154">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8862c-154">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="8862c-155">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8862c-155">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="8862c-156">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8862c-156">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="8862c-157">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="8862c-157">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
