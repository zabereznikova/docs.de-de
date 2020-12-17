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
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a><span data-ttu-id="f00fc-103">Breaking Changes in .NET-Bibliotheken für .NET Core 1.0 bis 3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-103">Core .NET libraries breaking changes in .NET Core 1.0-3.0</span></span>

<span data-ttu-id="f00fc-104">Die .NET-Kernbibliotheken stellen die von .NET Core verwendeten primitiven Typen sowie andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="f00fc-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="f00fc-105">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="f00fc-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="f00fc-106">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="f00fc-106">Breaking change</span></span> | <span data-ttu-id="f00fc-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f00fc-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="f00fc-108">Das Übergeben von GroupCollection an IEnumerable\<T> akzeptierende Erweiterungsmethoden erfordert Vermeidung von Mehrdeutigkeit</span><span class="sxs-lookup"><span data-stu-id="f00fc-108">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>](#passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation) | <span data-ttu-id="f00fc-109">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-109">3.0</span></span> |
| [<span data-ttu-id="f00fc-110">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="f00fc-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="f00fc-111">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-111">3.0</span></span> |
| [<span data-ttu-id="f00fc-112">Benutzerdefinierte EncoderFallbackBuffer-Instanzen können kein rekursives Fallback ausführen</span><span class="sxs-lookup"><span data-stu-id="f00fc-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="f00fc-113">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-113">3.0</span></span> |
| [<span data-ttu-id="f00fc-114">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="f00fc-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="f00fc-115">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-115">3.0</span></span> |
| [<span data-ttu-id="f00fc-116">Gleitkommaanalysevorgänge lösen keinen Fehler und keine OverflowException mehr aus</span><span class="sxs-lookup"><span data-stu-id="f00fc-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="f00fc-117">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-117">3.0</span></span> |
| [<span data-ttu-id="f00fc-118">InvalidAsynchronousStateException wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="f00fc-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="f00fc-119">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-119">3.0</span></span> |
| [<span data-ttu-id="f00fc-120">Ersetzen von falsch formatierten UTF-8-Bytesequenzen richtet sich nach Unicode-Vorgaben</span><span class="sxs-lookup"><span data-stu-id="f00fc-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="f00fc-121">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-121">3.0</span></span> |
| [<span data-ttu-id="f00fc-122">TypeDescriptionProviderAttribute wurde in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="f00fc-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="f00fc-123">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-123">3.0</span></span> |
| [<span data-ttu-id="f00fc-124">ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr</span><span class="sxs-lookup"><span data-stu-id="f00fc-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="f00fc-125">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-125">3.0</span></span> |
| [<span data-ttu-id="f00fc-126">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="f00fc-126">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="f00fc-127">3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-127">3.0</span></span> |
| [<span data-ttu-id="f00fc-128">Private Felder, die integrierten Strukturtypen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="f00fc-128">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="f00fc-129">2.1</span><span class="sxs-lookup"><span data-stu-id="f00fc-129">2.1</span></span> |
| [<span data-ttu-id="f00fc-130">Änderung des Standardwerts von UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="f00fc-130">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="f00fc-131">2.1</span><span class="sxs-lookup"><span data-stu-id="f00fc-131">2.1</span></span> |
| [<span data-ttu-id="f00fc-132">OpenSSL-Versionen unter macOS</span><span class="sxs-lookup"><span data-stu-id="f00fc-132">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="f00fc-133">2.1</span><span class="sxs-lookup"><span data-stu-id="f00fc-133">2.1</span></span> |
| [<span data-ttu-id="f00fc-134">UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="f00fc-134">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="f00fc-135">1.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-135">1.0</span></span> |
| [<span data-ttu-id="f00fc-136">Verarbeiten von Corrupted Process-State Exceptions wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="f00fc-136">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="f00fc-137">1.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-137">1.0</span></span> |
| [<span data-ttu-id="f00fc-138">UriBuilder-Eigenschaften werden führenden Zeichen nicht mehr vorangestellt</span><span class="sxs-lookup"><span data-stu-id="f00fc-138">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="f00fc-139">1.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-139">1.0</span></span> |
| [<span data-ttu-id="f00fc-140">Process.StartInfo löst InvalidOperationException für Prozesse aus, die Sie nicht gestartet haben</span><span class="sxs-lookup"><span data-stu-id="f00fc-140">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="f00fc-141">1.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-141">1.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="f00fc-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-142">.NET Core 3.0</span></span>

[!INCLUDE [disambiguate-generic-type-for-groupcollection](../../../includes/core-changes/corefx/3.0/disambiguate-generic-type-for-groupcollection.md)]

***

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

<span data-ttu-id="f00fc-143">\*\*_</span><span class="sxs-lookup"><span data-stu-id="f00fc-143">\*\*_</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="f00fc-144">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f00fc-144">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a><span data-ttu-id="f00fc-145">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="f00fc-145">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

<span data-ttu-id="f00fc-146">_\*\*</span><span class="sxs-lookup"><span data-stu-id="f00fc-146">_\*\*</span></span>
