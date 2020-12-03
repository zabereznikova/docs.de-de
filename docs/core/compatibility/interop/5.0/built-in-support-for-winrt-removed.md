---
title: 'Breaking Change: Integrierte Unterstützung für WinRT wird aus .NET entfernt'
description: Hier erfahren Sie mehr über den Interop-Breaking-Change in .NET 5.0, bei dem die integrierte Unterstützung für WinRT aus .NET entfernt wurde.
ms.date: 10/13/2020
ms.openlocfilehash: 61d8e26d06c232a7bfa1891a2159f5232f747b8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759482"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="3ab68-103">Integrierte Unterstützung für WinRT wird aus .NET entfernt</span><span class="sxs-lookup"><span data-stu-id="3ab68-103">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="3ab68-104">Die integrierte Unterstützung für die Nutzung von [WinRT-APIs (Windows Runtime)](/uwp/winrt-cref/winrt-type-system) in .NET wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="3ab68-104">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="3ab68-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3ab68-105">Version introduced</span></span>

<span data-ttu-id="3ab68-106">5.0</span><span class="sxs-lookup"><span data-stu-id="3ab68-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="3ab68-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3ab68-107">Change description</span></span>

<span data-ttu-id="3ab68-108">Zuvor konnte CoreCLR [Windows-Metadatendateien (WinMD)](/uwp/winrt-cref/winmd-files) verwenden, um WinRT-Typen zu aktivieren und zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="3ab68-108">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="3ab68-109">Ab .NET 5.0 kann CoreCLR WinMD-Dateien nicht mehr direkt nutzen.</span><span class="sxs-lookup"><span data-stu-id="3ab68-109">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="3ab68-110">Wenn Sie versuchen, auf eine nicht unterstützte Assembly zu verweisen, wird eine <xref:System.IO.FileNotFoundException> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ab68-110">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="3ab68-111">Wenn Sie eine WinRT-Klasse aktivieren, wird eine <xref:System.PlatformNotSupportedException> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ab68-111">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="3ab68-112">Dieser Breaking Change wurde aus den folgenden Gründen vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="3ab68-112">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="3ab68-113">WinRT kann jetzt unabhängig von der .NET-Runtime entwickelt und verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="3ab68-113">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="3ab68-114">Außerdem dient dies der Symmetrie mit Interopsystemen, die für andere Betriebssysteme wie iOS und Android bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3ab68-114">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="3ab68-115">Andere .NET-Features wie C#-Features, IL-Verknüpfungen (Intermediate Language) und die AOT-Kompilierung (Ahead-of-Time) können genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="3ab68-115">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="3ab68-116">Die .NET-Runtimecodebasis kann vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="3ab68-116">To simplify the .NET runtime codebase.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="3ab68-117">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3ab68-117">Recommended action</span></span>

- <span data-ttu-id="3ab68-118">Entfernen Sie Verweise auf das [Microsoft.Windows.SDK.Contracts-Paket](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span><span class="sxs-lookup"><span data-stu-id="3ab68-118">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span></span>  <span data-ttu-id="3ab68-119">Geben Sie stattdessen die Version der Windows-APIs an, auf die Sie über die `TargetFramework`-Eigenschaft des Projekts zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ab68-119">Instead, specify the version of the Windows APIs that you want to access via the `TargetFramework` property of the project.</span></span>  <span data-ttu-id="3ab68-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3ab68-120">For example:</span></span>

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- <span data-ttu-id="3ab68-121">Verwenden Sie die [C#/WinRT](/windows/uwp/csharp-winrt/)-Toolkette, um WinRT-APIs und Typen für .NET 5.0 und höheren Versionen zu generieren oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="3ab68-121">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types for .NET 5.0 and later versions.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="3ab68-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3ab68-122">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
