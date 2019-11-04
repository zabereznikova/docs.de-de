---
title: Breaking Changes bei CoreFx – .NET Core
description: Listet die Breaking Changes in der Basisklassenbibliothek .NET CoreFx auf.
ms.date: 09/20/2019
ms.openlocfilehash: 04ae857b5f46748ad57c742b6ccf421f57bc3138
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093431"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="a784d-103">Breaking Changes bei CoreFx</span><span class="sxs-lookup"><span data-stu-id="a784d-103">CoreFx breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a784d-104">Dieser Artikel wird aktuell überarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a784d-104">This article is under construction.</span></span> <span data-ttu-id="a784d-105">Nicht alle Breaking Changes für .NET Core werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a784d-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="a784d-106">Weitere Informationen zu Breaking Changes für .NET Core finden Sie in den jeweiligen [Issues zu Breaking Changes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) im Repository „dotnet/docs“ auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="a784d-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span>

<span data-ttu-id="a784d-107">Im Folgenden sind die Breaking Changes bei CoreFx in .NET Core aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a784d-107">The following is a list of CoreFx breaking changes by .NET Core version.</span></span> <span data-ttu-id="a784d-108">CoreFx stellt die von .NET Core verwendeten Primitiven und andere allgemeine Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="a784d-108">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

## <a name="net-core-30-preview-7"></a><span data-ttu-id="a784d-109">.NET Core 3.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="a784d-109">.NET Core 3.0 Preview 7</span></span>

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/jsonelement-api-changes.md)]

## <a name="net-core-30-preview-8"></a><span data-ttu-id="a784d-110">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="a784d-110">.NET Core 3.0 Preview 8</span></span>

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/jsonfactoryconverter-createconverter.md)]

## <a name="net-core-30-preview-9"></a><span data-ttu-id="a784d-111">.NET Core 3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="a784d-111">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Json serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/serializer-throws-notsupportedexception.md)]

## <a name="net-core-30"></a><span data-ttu-id="a784d-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a784d-112">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]
