---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 07/27/2020
ms.openlocfilehash: c8eb5ec7d2bb1879a38a18337463230c7b731d29
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137498"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="135b5-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="135b5-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="135b5-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="135b5-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="135b5-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="135b5-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="135b5-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="135b5-106">Breaking change</span></span> | <span data-ttu-id="135b5-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="135b5-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="135b5-108">Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht</span><span class="sxs-lookup"><span data-stu-id="135b5-108">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="135b5-109">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-109">5.0</span></span> |
| [<span data-ttu-id="135b5-110">IntPtr und UIntPtr implementieren IFormattable</span><span class="sxs-lookup"><span data-stu-id="135b5-110">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="135b5-111">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-111">5.0</span></span> |
| [<span data-ttu-id="135b5-112">PrincipalPermissionAttribute ist als Fehler veraltet</span><span class="sxs-lookup"><span data-stu-id="135b5-112">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="135b5-113">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-113">5.0</span></span> |
| [<span data-ttu-id="135b5-114">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="135b5-114">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="135b5-115">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-115">5.0</span></span> |
| [<span data-ttu-id="135b5-116">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="135b5-116">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="135b5-117">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-117">5.0</span></span> |
| [<span data-ttu-id="135b5-118">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="135b5-118">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="135b5-119">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-119">5.0</span></span> |
| [<span data-ttu-id="135b5-120">Das ActivityIdFormat-Standardformat ist W3C</span><span class="sxs-lookup"><span data-stu-id="135b5-120">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="135b5-121">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-121">5.0</span></span> |
| [<span data-ttu-id="135b5-122">Behavior Change für Vector2.Lerp und Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="135b5-122">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="135b5-123">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-123">5.0</span></span> |
| <span data-ttu-id="135b5-124">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="135b5-124">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="135b5-125">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-125">5.0</span></span> |
| [<span data-ttu-id="135b5-126">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="135b5-126">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="135b5-127">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-127">5.0</span></span> |
| [<span data-ttu-id="135b5-128">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="135b5-128">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="135b5-129">5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-129">5.0</span></span> |
| [<span data-ttu-id="135b5-130">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="135b5-130">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="135b5-131">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-131">3.0</span></span> |
| [<span data-ttu-id="135b5-132">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="135b5-132">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="135b5-133">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-133">3.0</span></span> |
| [<span data-ttu-id="135b5-134">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="135b5-134">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="135b5-135">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-135">3.0</span></span> |
| [<span data-ttu-id="135b5-136">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="135b5-136">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="135b5-137">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-137">3.0</span></span> |
| [<span data-ttu-id="135b5-138">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="135b5-138">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="135b5-139">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-139">3.0</span></span> |
| [<span data-ttu-id="135b5-140">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="135b5-140">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="135b5-141">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-141">3.0</span></span> |
| [<span data-ttu-id="135b5-142">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="135b5-142">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="135b5-143">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-143">3.0</span></span> |
| [<span data-ttu-id="135b5-144">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="135b5-144">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="135b5-145">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-145">3.0</span></span> |
| [<span data-ttu-id="135b5-146">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="135b5-146">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="135b5-147">3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-147">3.0</span></span> |
| [<span data-ttu-id="135b5-148">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="135b5-148">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="135b5-149">2.1</span><span class="sxs-lookup"><span data-stu-id="135b5-149">2.1</span></span> |
| [<span data-ttu-id="135b5-150">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="135b5-150">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="135b5-151">2.1</span><span class="sxs-lookup"><span data-stu-id="135b5-151">2.1</span></span> |
| [<span data-ttu-id="135b5-152">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="135b5-152">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="135b5-153">2.1</span><span class="sxs-lookup"><span data-stu-id="135b5-153">2.1</span></span> |
| [<span data-ttu-id="135b5-154">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="135b5-154">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="135b5-155">1.0</span><span class="sxs-lookup"><span data-stu-id="135b5-155">1.0</span></span> |
| [<span data-ttu-id="135b5-156">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="135b5-156">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="135b5-157">1.0</span><span class="sxs-lookup"><span data-stu-id="135b5-157">1.0</span></span> |
| [<span data-ttu-id="135b5-158">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="135b5-158">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="135b5-159">1.0</span><span class="sxs-lookup"><span data-stu-id="135b5-159">1.0</span></span> |
| [<span data-ttu-id="135b5-160">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="135b5-160">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="135b5-161">1.0</span><span class="sxs-lookup"><span data-stu-id="135b5-161">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="135b5-162">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="135b5-162">.NET 5.0</span></span>

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

***

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

***

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="135b5-163">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="135b5-163">.NET Core 3.0</span></span>

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

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="135b5-164">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="135b5-164">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="135b5-165">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="135b5-165">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
