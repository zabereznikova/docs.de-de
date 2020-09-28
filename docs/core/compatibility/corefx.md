---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 07/27/2020
ms.openlocfilehash: c3207ac7630d794f77c793cc6d1d52e158c0c084
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738819"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="3be02-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="3be02-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="3be02-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="3be02-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="3be02-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="3be02-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="3be02-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="3be02-106">Breaking change</span></span> | <span data-ttu-id="3be02-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3be02-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="3be02-108">Parameternamen in RC1 wurden geändert</span><span class="sxs-lookup"><span data-stu-id="3be02-108">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="3be02-109">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-109">5.0</span></span> |
| [<span data-ttu-id="3be02-110">OSPlatform-Attribute wurden umbenannt oder entfernt</span><span class="sxs-lookup"><span data-stu-id="3be02-110">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="3be02-111">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-111">5.0</span></span> |
| [<span data-ttu-id="3be02-112">Thread.Abort ist veraltet</span><span class="sxs-lookup"><span data-stu-id="3be02-112">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="3be02-113">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-113">5.0</span></span> |
| [<span data-ttu-id="3be02-114">Veraltete Eigenschaften in ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="3be02-114">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="3be02-115">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-115">5.0</span></span> |
| [<span data-ttu-id="3be02-116">Hardwareintrinsische IsSupported-Überprüfungen können für geschachtelte Typen abweichen</span><span class="sxs-lookup"><span data-stu-id="3be02-116">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="3be02-117">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-117">5.0</span></span> |
| [<span data-ttu-id="3be02-118">Änderung von Parameternamen in Referenzassemblys</span><span class="sxs-lookup"><span data-stu-id="3be02-118">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="3be02-119">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-119">5.0</span></span> |
| [<span data-ttu-id="3be02-120">Ordnungsgemäße Analyse von URI-Pfaden mit Nicht-ASCII-Zeichen unter UNIX</span><span class="sxs-lookup"><span data-stu-id="3be02-120">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="3be02-121">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-121">5.0</span></span> |
| [<span data-ttu-id="3be02-122">URI-Erkennung von UNC-Pfaden unter UNIX</span><span class="sxs-lookup"><span data-stu-id="3be02-122">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="3be02-123">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-123">5.0</span></span> |
| [<span data-ttu-id="3be02-124">Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion</span><span class="sxs-lookup"><span data-stu-id="3be02-124">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="3be02-125">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-125">5.0</span></span> |
| [<span data-ttu-id="3be02-126">Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht</span><span class="sxs-lookup"><span data-stu-id="3be02-126">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="3be02-127">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-127">5.0</span></span> |
| [<span data-ttu-id="3be02-128">IntPtr und UIntPtr implementieren IFormattable</span><span class="sxs-lookup"><span data-stu-id="3be02-128">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="3be02-129">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-129">5.0</span></span> |
| [<span data-ttu-id="3be02-130">PrincipalPermissionAttribute ist als Fehler veraltet</span><span class="sxs-lookup"><span data-stu-id="3be02-130">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="3be02-131">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-131">5.0</span></span> |
| [<span data-ttu-id="3be02-132">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="3be02-132">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="3be02-133">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-133">5.0</span></span> |
| [<span data-ttu-id="3be02-134">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="3be02-134">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="3be02-135">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-135">5.0</span></span> |
| [<span data-ttu-id="3be02-136">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="3be02-136">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="3be02-137">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-137">5.0</span></span> |
| [<span data-ttu-id="3be02-138">Das ActivityIdFormat-Standardformat ist W3C</span><span class="sxs-lookup"><span data-stu-id="3be02-138">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="3be02-139">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-139">5.0</span></span> |
| [<span data-ttu-id="3be02-140">Behavior Change für Vector2.Lerp und Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="3be02-140">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="3be02-141">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-141">5.0</span></span> |
| <span data-ttu-id="3be02-142">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="3be02-142">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="3be02-143">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-143">5.0</span></span> |
| [<span data-ttu-id="3be02-144">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="3be02-144">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="3be02-145">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-145">5.0</span></span> |
| [<span data-ttu-id="3be02-146">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="3be02-146">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="3be02-147">5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-147">5.0</span></span> |
| [<span data-ttu-id="3be02-148">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="3be02-148">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="3be02-149">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-149">3.0</span></span> |
| [<span data-ttu-id="3be02-150">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="3be02-150">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="3be02-151">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-151">3.0</span></span> |
| [<span data-ttu-id="3be02-152">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="3be02-152">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="3be02-153">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-153">3.0</span></span> |
| [<span data-ttu-id="3be02-154">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="3be02-154">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="3be02-155">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-155">3.0</span></span> |
| [<span data-ttu-id="3be02-156">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="3be02-156">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="3be02-157">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-157">3.0</span></span> |
| [<span data-ttu-id="3be02-158">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="3be02-158">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="3be02-159">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-159">3.0</span></span> |
| [<span data-ttu-id="3be02-160">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="3be02-160">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="3be02-161">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-161">3.0</span></span> |
| [<span data-ttu-id="3be02-162">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="3be02-162">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="3be02-163">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-163">3.0</span></span> |
| [<span data-ttu-id="3be02-164">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="3be02-164">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="3be02-165">3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-165">3.0</span></span> |
| [<span data-ttu-id="3be02-166">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="3be02-166">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="3be02-167">2.1</span><span class="sxs-lookup"><span data-stu-id="3be02-167">2.1</span></span> |
| [<span data-ttu-id="3be02-168">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="3be02-168">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="3be02-169">2.1</span><span class="sxs-lookup"><span data-stu-id="3be02-169">2.1</span></span> |
| [<span data-ttu-id="3be02-170">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="3be02-170">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="3be02-171">2.1</span><span class="sxs-lookup"><span data-stu-id="3be02-171">2.1</span></span> |
| [<span data-ttu-id="3be02-172">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="3be02-172">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="3be02-173">1.0</span><span class="sxs-lookup"><span data-stu-id="3be02-173">1.0</span></span> |
| [<span data-ttu-id="3be02-174">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="3be02-174">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="3be02-175">1.0</span><span class="sxs-lookup"><span data-stu-id="3be02-175">1.0</span></span> |
| [<span data-ttu-id="3be02-176">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="3be02-176">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="3be02-177">1.0</span><span class="sxs-lookup"><span data-stu-id="3be02-177">1.0</span></span> |
| [<span data-ttu-id="3be02-178">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="3be02-178">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="3be02-179">1.0</span><span class="sxs-lookup"><span data-stu-id="3be02-179">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="3be02-180">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3be02-180">.NET 5.0</span></span>

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

***

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

***

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

***

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

***

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

***

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

***

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

***

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

***

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="3be02-181">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3be02-181">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="3be02-182">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3be02-182">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="3be02-183">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3be02-183">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
