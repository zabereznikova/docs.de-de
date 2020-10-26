---
title: Breaking Changes hinsichtlich der Basisklassenbibliothek
description: Listet die Breaking Changes in .NET-Kernbibliotheken auf.
ms.date: 07/27/2020
ms.openlocfilehash: 3ecf0e81a3adef097aafb760dc44498d7263f0b6
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050563"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="98cd4-103">Breaking Changes und .NET-Kernbibliotheken</span><span class="sxs-lookup"><span data-stu-id="98cd4-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="98cd4-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="98cd4-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="98cd4-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="98cd4-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="98cd4-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="98cd4-106">Breaking change</span></span> | <span data-ttu-id="98cd4-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="98cd4-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="98cd4-108">Der Wert von FrameworkDescription entspricht .NET anstelle von .NET Core</span><span class="sxs-lookup"><span data-stu-id="98cd4-108">FrameworkDescription's value is .NET instead of .NET Core</span></span>](#frameworkdescriptions-value-is-net-instead-of-net-core) | <span data-ttu-id="98cd4-109">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-109">5.0</span></span> |
| [<span data-ttu-id="98cd4-110">Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei</span><span class="sxs-lookup"><span data-stu-id="98cd4-110">Assembly-related API behavior changes for single-file publishing format</span></span>](#assembly-related-api-behavior-changes-for-single-file-publishing-format) | <span data-ttu-id="98cd4-111">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-111">5.0</span></span> |
| [<span data-ttu-id="98cd4-112">Die Reihenfolge der Tags in Activity.Tags wird umgekehrt</span><span class="sxs-lookup"><span data-stu-id="98cd4-112">Order of tags in Activity.Tags is reversed</span></span>](#order-of-tags-in-activitytags-is-reversed) | <span data-ttu-id="98cd4-113">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-113">5.0</span></span> |
| [<span data-ttu-id="98cd4-114">Parameternamen in RC1 wurden geändert</span><span class="sxs-lookup"><span data-stu-id="98cd4-114">Parameter names changed in RC1</span></span>](#parameter-names-changed-in-rc1) | <span data-ttu-id="98cd4-115">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-115">5.0</span></span> |
| [<span data-ttu-id="98cd4-116">OSPlatform-Attribute wurden umbenannt oder entfernt</span><span class="sxs-lookup"><span data-stu-id="98cd4-116">OSPlatform attributes renamed or removed</span></span>](#osplatform-attributes-renamed-or-removed) | <span data-ttu-id="98cd4-117">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-117">5.0</span></span> |
| [<span data-ttu-id="98cd4-118">Thread.Abort ist veraltet</span><span class="sxs-lookup"><span data-stu-id="98cd4-118">Thread.Abort is obsolete</span></span>](#threadabort-is-obsolete) | <span data-ttu-id="98cd4-119">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-119">5.0</span></span> |
| [<span data-ttu-id="98cd4-120">Veraltete Eigenschaften in ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="98cd4-120">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="98cd4-121">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-121">5.0</span></span> |
| [<span data-ttu-id="98cd4-122">Hardwareintrinsische IsSupported-Überprüfungen können für geschachtelte Typen abweichen</span><span class="sxs-lookup"><span data-stu-id="98cd4-122">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="98cd4-123">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-123">5.0</span></span> |
| [<span data-ttu-id="98cd4-124">Änderung von Parameternamen in Referenzassemblys</span><span class="sxs-lookup"><span data-stu-id="98cd4-124">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="98cd4-125">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-125">5.0</span></span> |
| [<span data-ttu-id="98cd4-126">Ordnungsgemäße Analyse von URI-Pfaden mit Nicht-ASCII-Zeichen unter UNIX</span><span class="sxs-lookup"><span data-stu-id="98cd4-126">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="98cd4-127">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-127">5.0</span></span> |
| [<span data-ttu-id="98cd4-128">URI-Erkennung von UNC-Pfaden unter UNIX</span><span class="sxs-lookup"><span data-stu-id="98cd4-128">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="98cd4-129">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-129">5.0</span></span> |
| [<span data-ttu-id="98cd4-130">Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion</span><span class="sxs-lookup"><span data-stu-id="98cd4-130">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="98cd4-131">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-131">5.0</span></span> |
| [<span data-ttu-id="98cd4-132">Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht</span><span class="sxs-lookup"><span data-stu-id="98cd4-132">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="98cd4-133">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-133">5.0</span></span> |
| [<span data-ttu-id="98cd4-134">IntPtr und UIntPtr implementieren IFormattable</span><span class="sxs-lookup"><span data-stu-id="98cd4-134">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="98cd4-135">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-135">5.0</span></span> |
| [<span data-ttu-id="98cd4-136">PrincipalPermissionAttribute ist als Fehler veraltet</span><span class="sxs-lookup"><span data-stu-id="98cd4-136">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="98cd4-137">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-137">5.0</span></span> |
| [<span data-ttu-id="98cd4-138">BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten</span><span class="sxs-lookup"><span data-stu-id="98cd4-138">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="98cd4-139">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-139">5.0</span></span> |
| [<span data-ttu-id="98cd4-140">UTF-7-Codepfade sind veraltet</span><span class="sxs-lookup"><span data-stu-id="98cd4-140">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="98cd4-141">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-141">5.0</span></span> |
| [<span data-ttu-id="98cd4-142">Vector\<T> löst immer eine NotSupportedException für nicht unterstützte Typen aus</span><span class="sxs-lookup"><span data-stu-id="98cd4-142">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="98cd4-143">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-143">5.0</span></span> |
| [<span data-ttu-id="98cd4-144">Das ActivityIdFormat-Standardformat ist W3C</span><span class="sxs-lookup"><span data-stu-id="98cd4-144">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="98cd4-145">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-145">5.0</span></span> |
| [<span data-ttu-id="98cd4-146">Behavior Change für Vector2.Lerp und Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="98cd4-146">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="98cd4-147">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-147">5.0</span></span> |
| <span data-ttu-id="98cd4-148">[Die CompareGreaterThan-Methoden von SSE und SSE2 behandeln NaN-Eingaben ordnungsgemäß](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs).</span><span class="sxs-lookup"><span data-stu-id="98cd4-148">[SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs)</span></span> | <span data-ttu-id="98cd4-149">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-149">5.0</span></span> |
| [<span data-ttu-id="98cd4-150">CounterSet.CreateCounterSetInstance löst jetzt InvalidOperationException aus, wenn die Instanz bereits vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="98cd4-150">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="98cd4-151">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-151">5.0</span></span> |
| [<span data-ttu-id="98cd4-152">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="98cd4-152">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="98cd4-153">5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-153">5.0</span></span> |
| [<span data-ttu-id="98cd4-154">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="98cd4-154">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="98cd4-155">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-155">3.0</span></span> |
| [<span data-ttu-id="98cd4-156">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="98cd4-156">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="98cd4-157">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-157">3.0</span></span> |
| [<span data-ttu-id="98cd4-158">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="98cd4-158">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="98cd4-159">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-159">3.0</span></span> |
| [<span data-ttu-id="98cd4-160">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="98cd4-160">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="98cd4-161">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-161">3.0</span></span> |
| [<span data-ttu-id="98cd4-162">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="98cd4-162">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="98cd4-163">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-163">3.0</span></span> |
| [<span data-ttu-id="98cd4-164">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="98cd4-164">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="98cd4-165">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-165">3.0</span></span> |
| [<span data-ttu-id="98cd4-166">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="98cd4-166">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="98cd4-167">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-167">3.0</span></span> |
| [<span data-ttu-id="98cd4-168">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="98cd4-168">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="98cd4-169">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-169">3.0</span></span> |
| [<span data-ttu-id="98cd4-170">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="98cd4-170">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="98cd4-171">3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-171">3.0</span></span> |
| [<span data-ttu-id="98cd4-172">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="98cd4-172">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="98cd4-173">2.1</span><span class="sxs-lookup"><span data-stu-id="98cd4-173">2.1</span></span> |
| [<span data-ttu-id="98cd4-174">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="98cd4-174">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="98cd4-175">2.1</span><span class="sxs-lookup"><span data-stu-id="98cd4-175">2.1</span></span> |
| [<span data-ttu-id="98cd4-176">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="98cd4-176">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="98cd4-177">2.1</span><span class="sxs-lookup"><span data-stu-id="98cd4-177">2.1</span></span> |
| [<span data-ttu-id="98cd4-178">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="98cd4-178">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="98cd4-179">1.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-179">1.0</span></span> |
| [<span data-ttu-id="98cd4-180">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="98cd4-180">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="98cd4-181">1.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-181">1.0</span></span> |
| [<span data-ttu-id="98cd4-182">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="98cd4-182">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="98cd4-183">1.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-183">1.0</span></span> |
| [<span data-ttu-id="98cd4-184">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="98cd4-184">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="98cd4-185">1.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-185">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="98cd4-186">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-186">.NET 5.0</span></span>

[!INCLUDE [frameworkdescription-returns-net-not-net-core](../../../includes/core-changes/corefx/5.0/frameworkdescription-returns-net-not-net-core.md)]

***

[!INCLUDE [assembly-api-behavior-changes-for-single-file-publish](../../../includes/core-changes/corefx/5.0/assembly-api-behavior-changes-for-single-file-publish.md)]

***

[!INCLUDE [reverse-order-of-tags-in-activity-property](../../../includes/core-changes/corefx/5.0/reverse-order-of-tags-in-activity-property.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="98cd4-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-187">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="98cd4-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="98cd4-188">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="98cd4-189">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="98cd4-189">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
