---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 07/27/2020
ms.openlocfilehash: 900fd4e0e071f19aa286dec84632006870822f26
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434944"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="060d8-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="060d8-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="060d8-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="060d8-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="060d8-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="060d8-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="060d8-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="060d8-106">Breaking change</span></span> | <span data-ttu-id="060d8-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="060d8-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="060d8-108">APIs für den globalen Assemblycache sind veraltet</span><span class="sxs-lookup"><span data-stu-id="060d8-108">Global assembly cache APIs are obsolete</span></span>](#global-assembly-cache-apis-are-obsolete) | <span data-ttu-id="060d8-109">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-109">5.0</span></span> |
| [<span data-ttu-id="060d8-110">Remoting-APIs sind veraltet</span><span class="sxs-lookup"><span data-stu-id="060d8-110">Remoting APIs are obsolete</span></span>](#remoting-apis-are-obsolete) | <span data-ttu-id="060d8-111">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-111">5.0</span></span> |
| [<span data-ttu-id="060d8-112">Die meisten Codezugriffssicherheit-APIs sind veraltet</span><span class="sxs-lookup"><span data-stu-id="060d8-112">Most code access security APIs are obsolete</span></span>](#most-code-access-security-apis-are-obsolete) | <span data-ttu-id="060d8-113">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-113">5.0</span></span> |
| [<span data-ttu-id="060d8-114">Veraltete APIs ohne Standarddiagnose-IDs</span><span class="sxs-lookup"><span data-stu-id="060d8-114">API obsoletions with non-default diagnostic IDs</span></span>](#api-obsoletions-with-non-default-diagnostic-ids) | <span data-ttu-id="060d8-115">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-115">5.0</span></span> |
| [<span data-ttu-id="060d8-116">Der Wert von FrameworkDescription entspricht .NET anstelle von .NET Core</span><span class="sxs-lookup"><span data-stu-id="060d8-116">FrameworkDescription's value is .NET instead of .NET Core</span></span>](#frameworkdescriptions-value-is-net-instead-of-net-core) | <span data-ttu-id="060d8-117">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-117">5.0</span></span> |
| [<span data-ttu-id="060d8-118">Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei</span><span class="sxs-lookup"><span data-stu-id="060d8-118">Assembly-related API behavior changes for single-file publishing format</span></span>](#assembly-related-api-behavior-changes-for-single-file-publishing-format) | <span data-ttu-id="060d8-119">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-119">5.0</span></span> |
| [<span data-ttu-id="060d8-120">Die Reihenfolge der Tags in Activity.Tags wird umgekehrt</span><span class="sxs-lookup"><span data-stu-id="060d8-120">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="060d8-121">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-121">5.0</span></span> |
| [<span data-ttu-id="060d8-122">Parameternamen in RC1 wurden geändert</span><span class="sxs-lookup"><span data-stu-id="060d8-122">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="060d8-123">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-123">5.0</span></span> |
| [<span data-ttu-id="060d8-124">OSPlatform-Attribute wurden umbenannt oder entfernt</span><span class="sxs-lookup"><span data-stu-id="060d8-124">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="060d8-125">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-125">5.0</span></span> |
| [<span data-ttu-id="060d8-126">Thread.Abort ist veraltet</span><span class="sxs-lookup"><span data-stu-id="060d8-126">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="060d8-127">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-127">5.0</span></span> |
| [<span data-ttu-id="060d8-128">Veraltete Eigenschaften in ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="060d8-128">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="060d8-129">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-129">5.0</span></span> |
| [<span data-ttu-id="060d8-130">Hardwareintrinsische IsSupported-Überprüfungen können für geschachtelte Typen abweichen</span><span class="sxs-lookup"><span data-stu-id="060d8-130">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="060d8-131">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-131">5.0</span></span> |
| [<span data-ttu-id="060d8-132">Änderung von Parameternamen in Referenzassemblys</span><span class="sxs-lookup"><span data-stu-id="060d8-132">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="060d8-133">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-133">5.0</span></span> |
| [<span data-ttu-id="060d8-134">Ordnungsgemäße Analyse von URI-Pfaden mit Nicht-ASCII-Zeichen unter UNIX</span><span class="sxs-lookup"><span data-stu-id="060d8-134">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="060d8-135">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-135">5.0</span></span> |
| [<span data-ttu-id="060d8-136">URI-Erkennung von UNC-Pfaden unter UNIX</span><span class="sxs-lookup"><span data-stu-id="060d8-136">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="060d8-137">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-137">5.0</span></span> |
| [<span data-ttu-id="060d8-138">Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion</span><span class="sxs-lookup"><span data-stu-id="060d8-138">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="060d8-139">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-139">5.0</span></span> |
| [<span data-ttu-id="060d8-140">Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht</span><span class="sxs-lookup"><span data-stu-id="060d8-140">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="060d8-141">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-141">5.0</span></span> |
| [<span data-ttu-id="060d8-142">IntPtr und UIntPtr implementieren IFormattable</span><span class="sxs-lookup"><span data-stu-id="060d8-142">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="060d8-143">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-143">5.0</span></span> |
| [<span data-ttu-id="060d8-144">PrincipalPermissionAttribute ist als Fehler veraltet</span><span class="sxs-lookup"><span data-stu-id="060d8-144">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="060d8-145">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-145">5.0</span></span> |
| [<span data-ttu-id="060d8-146">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="060d8-146">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="060d8-147">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-147">5.0</span></span> |
| [<span data-ttu-id="060d8-148">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="060d8-148">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="060d8-149">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-149">5.0</span></span> |
| [<span data-ttu-id="060d8-150">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="060d8-150">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="060d8-151">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-151">5.0</span></span> |
| [<span data-ttu-id="060d8-152">Das ActivityIdFormat-Standardformat ist W3C</span><span class="sxs-lookup"><span data-stu-id="060d8-152">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="060d8-153">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-153">5.0</span></span> |
| [<span data-ttu-id="060d8-154">Behavior Change für Vector2.Lerp und Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="060d8-154">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="060d8-155">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-155">5.0</span></span> |
| <span data-ttu-id="060d8-156">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="060d8-156">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="060d8-157">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-157">5.0</span></span> |
| [<span data-ttu-id="060d8-158">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="060d8-158">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="060d8-159">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-159">5.0</span></span> |
| [<span data-ttu-id="060d8-160">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="060d8-160">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="060d8-161">5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-161">5.0</span></span> |
| [<span data-ttu-id="060d8-162">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="060d8-162">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="060d8-163">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-163">3.0</span></span> |
| [<span data-ttu-id="060d8-164">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="060d8-164">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="060d8-165">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-165">3.0</span></span> |
| [<span data-ttu-id="060d8-166">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="060d8-166">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="060d8-167">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-167">3.0</span></span> |
| [<span data-ttu-id="060d8-168">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="060d8-168">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="060d8-169">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-169">3.0</span></span> |
| [<span data-ttu-id="060d8-170">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="060d8-170">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="060d8-171">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-171">3.0</span></span> |
| [<span data-ttu-id="060d8-172">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="060d8-172">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="060d8-173">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-173">3.0</span></span> |
| [<span data-ttu-id="060d8-174">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="060d8-174">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="060d8-175">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-175">3.0</span></span> |
| [<span data-ttu-id="060d8-176">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="060d8-176">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="060d8-177">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-177">3.0</span></span> |
| [<span data-ttu-id="060d8-178">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="060d8-178">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="060d8-179">3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-179">3.0</span></span> |
| [<span data-ttu-id="060d8-180">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="060d8-180">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="060d8-181">2.1</span><span class="sxs-lookup"><span data-stu-id="060d8-181">2.1</span></span> |
| [<span data-ttu-id="060d8-182">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="060d8-182">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="060d8-183">2.1</span><span class="sxs-lookup"><span data-stu-id="060d8-183">2.1</span></span> |
| [<span data-ttu-id="060d8-184">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="060d8-184">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="060d8-185">2.1</span><span class="sxs-lookup"><span data-stu-id="060d8-185">2.1</span></span> |
| [<span data-ttu-id="060d8-186">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="060d8-186">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="060d8-187">1.0</span><span class="sxs-lookup"><span data-stu-id="060d8-187">1.0</span></span> |
| [<span data-ttu-id="060d8-188">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="060d8-188">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="060d8-189">1.0</span><span class="sxs-lookup"><span data-stu-id="060d8-189">1.0</span></span> |
| [<span data-ttu-id="060d8-190">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="060d8-190">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="060d8-191">1.0</span><span class="sxs-lookup"><span data-stu-id="060d8-191">1.0</span></span> |
| [<span data-ttu-id="060d8-192">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="060d8-192">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="060d8-193">1.0</span><span class="sxs-lookup"><span data-stu-id="060d8-193">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="060d8-194">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="060d8-194">.NET 5.0</span></span>

[!INCLUDE [remoting-apis-obsolete](../../../includes/core-changes/corefx/5.0/remoting-apis-obsolete.md)]

***

[!INCLUDE [globalassemblycache-property-obsolete](../../../includes/core-changes/corefx/5.0/global-assembly-cache-apis-obsolete.md)]

<span data-ttu-id="060d8-195">\*\*_</span><span class="sxs-lookup"><span data-stu-id="060d8-195">\*\*_</span></span>

[!INCLUDE [code-access-security-apis-obsolete](../../../includes/core-changes/corefx/5.0/code-access-security-apis-obsolete.md)]

_*_

[!INCLUDE [obsolete-apis-with-custom-diagnostics](../../../includes/core-changes/corefx/5.0/obsolete-apis-with-custom-diagnostics.md)]

_*_

[!INCLUDE [frameworkdescription-returns-net-not-net-core](../../../includes/core-changes/corefx/5.0/frameworkdescription-returns-net-not-net-core.md)]

_*_

[!INCLUDE [assembly-api-behavior-changes-for-single-file-publish](../../../includes/core-changes/corefx/5.0/assembly-api-behavior-changes-for-single-file-publish.md)]

_*_

[!INCLUDE [reverse-order-of-tags-in-activity-property](../../../includes/core-changes/corefx/5.0/reverse-order-of-tags-in-activity-property.md)]

_*_

[!INCLUDE [reference-assembly-parameter-names-rc1](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names-rc1.md)]

_*_

[!INCLUDE [os-platform-attributes-renamed](../../../includes/core-changes/corefx/5.0/os-platform-attributes-renamed.md)]

_*_

[!INCLUDE [thread-abort-obsolete](../../../includes/core-changes/corefx/5.0/thread-abort-obsolete.md)]

_*_

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

_*_

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

_*_

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

_*_

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

_*_

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

_*_

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

_*_

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

_*_

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

_*_

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

_*_

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

_*_

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

_*_

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

_*_

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

_*_

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

_*_

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

_*_

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

_*_

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

_*_

## <a name="net-core-30"></a><span data-ttu-id="060d8-196">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="060d8-196">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

_*_

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

## <a name="net-core-21"></a><span data-ttu-id="060d8-197">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="060d8-197">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="060d8-198">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="060d8-198">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="060d8-199">_\*\*</span><span class="sxs-lookup"><span data-stu-id="060d8-199">_\*\*</span></span>
