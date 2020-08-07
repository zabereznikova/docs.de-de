---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 07/27/2020
ms.openlocfilehash: 558aa1d76831cd15e2028c17d2b0b2e82f64ef9a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517325"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="a7433-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="a7433-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="a7433-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="a7433-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="a7433-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="a7433-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a7433-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="a7433-106">Breaking change</span></span> | <span data-ttu-id="a7433-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a7433-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="a7433-108">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="a7433-108">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="a7433-109">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-109">5.0</span></span> |
| [<span data-ttu-id="a7433-110">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="a7433-110">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="a7433-111">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-111">5.0</span></span> |
| [<span data-ttu-id="a7433-112">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="a7433-112">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="a7433-113">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-113">5.0</span></span> |
| [<span data-ttu-id="a7433-114">Das ActivityIdFormat-Standardformat ist W3C</span><span class="sxs-lookup"><span data-stu-id="a7433-114">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="a7433-115">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-115">5.0</span></span> |
| [<span data-ttu-id="a7433-116">Behavior Change für Vector2.Lerp und Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="a7433-116">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="a7433-117">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-117">5.0</span></span> |
| <span data-ttu-id="a7433-118">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="a7433-118">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="a7433-119">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-119">5.0</span></span> |
| [<span data-ttu-id="a7433-120">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="a7433-120">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="a7433-121">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-121">5.0</span></span> |
| [<span data-ttu-id="a7433-122">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="a7433-122">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="a7433-123">5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-123">5.0</span></span> |
| [<span data-ttu-id="a7433-124">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="a7433-124">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="a7433-125">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-125">3.0</span></span> |
| [<span data-ttu-id="a7433-126">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="a7433-126">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="a7433-127">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-127">3.0</span></span> |
| [<span data-ttu-id="a7433-128">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="a7433-128">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="a7433-129">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-129">3.0</span></span> |
| [<span data-ttu-id="a7433-130">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="a7433-130">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="a7433-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-131">3.0</span></span> |
| [<span data-ttu-id="a7433-132">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="a7433-132">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="a7433-133">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-133">3.0</span></span> |
| [<span data-ttu-id="a7433-134">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="a7433-134">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="a7433-135">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-135">3.0</span></span> |
| [<span data-ttu-id="a7433-136">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="a7433-136">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="a7433-137">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-137">3.0</span></span> |
| [<span data-ttu-id="a7433-138">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="a7433-138">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="a7433-139">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-139">3.0</span></span> |
| [<span data-ttu-id="a7433-140">Änderung der Semantik von (string)null in Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="a7433-140">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="a7433-141">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-141">3.0</span></span> |
| [<span data-ttu-id="a7433-142">JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf</span><span class="sxs-lookup"><span data-stu-id="a7433-142">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="a7433-143">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-143">3.0</span></span> |
| [<span data-ttu-id="a7433-144">Änderung der JsonFactoryConverter.CreateConverter-Signatur</span><span class="sxs-lookup"><span data-stu-id="a7433-144">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="a7433-145">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-145">3.0</span></span> |
| [<span data-ttu-id="a7433-146">Änderungen der JsonElement-API</span><span class="sxs-lookup"><span data-stu-id="a7433-146">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="a7433-147">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-147">3.0</span></span> |
| [<span data-ttu-id="a7433-148">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="a7433-148">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="a7433-149">3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-149">3.0</span></span> |
| [<span data-ttu-id="a7433-150">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="a7433-150">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="a7433-151">2.1</span><span class="sxs-lookup"><span data-stu-id="a7433-151">2.1</span></span> |
| [<span data-ttu-id="a7433-152">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="a7433-152">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="a7433-153">2.1</span><span class="sxs-lookup"><span data-stu-id="a7433-153">2.1</span></span> |
| [<span data-ttu-id="a7433-154">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="a7433-154">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="a7433-155">2.1</span><span class="sxs-lookup"><span data-stu-id="a7433-155">2.1</span></span> |
| [<span data-ttu-id="a7433-156">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="a7433-156">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="a7433-157">1.0</span><span class="sxs-lookup"><span data-stu-id="a7433-157">1.0</span></span> |
| [<span data-ttu-id="a7433-158">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a7433-158">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="a7433-159">1.0</span><span class="sxs-lookup"><span data-stu-id="a7433-159">1.0</span></span> |
| [<span data-ttu-id="a7433-160">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="a7433-160">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="a7433-161">1.0</span><span class="sxs-lookup"><span data-stu-id="a7433-161">1.0</span></span> |
| [<span data-ttu-id="a7433-162">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="a7433-162">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="a7433-163">1.0</span><span class="sxs-lookup"><span data-stu-id="a7433-163">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="a7433-164">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a7433-164">.NET 5.0</span></span>

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

***

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

***

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="a7433-165">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a7433-165">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="a7433-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a7433-166">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="a7433-167">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="a7433-167">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
