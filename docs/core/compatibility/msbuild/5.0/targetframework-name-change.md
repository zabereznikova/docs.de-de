---
title: 'Breaking Change: TargetFramework-Änderung von „netcoreapp“ in „net“'
description: Hier erfahren Sie mehr über den Breaking Change für .NET 5.0, durch den der Wert der MSBuild-Eigenschaft „TargetFramework“ von „netcoreapp3.1“ in „net5.0“ geändert wurde.
ms.date: 10/17/2020
ms.openlocfilehash: c3b39a36548d58d6ed75fd8b1c84b0cccfc738f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759398"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="1a062-103">TargetFramework-Änderung von „netcoreapp“ in „net“</span><span class="sxs-lookup"><span data-stu-id="1a062-103">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="1a062-104">Der Wert der MSBuild-Eigenschaft `TargetFramework` wurde von `netcoreapp3.1` in `net5.0` geändert.</span><span class="sxs-lookup"><span data-stu-id="1a062-104">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="1a062-105">Dadurch wird möglicherweise Code unterbrochen, der von der Verarbeitung des Werts von `TargetFramework` abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="1a062-105">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1a062-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1a062-106">Version introduced</span></span>

<span data-ttu-id="1a062-107">5.0</span><span class="sxs-lookup"><span data-stu-id="1a062-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="1a062-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="1a062-108">Change description</span></span>

<span data-ttu-id="1a062-109">In .NET Core 1.0 bis 3.1 beginnt der Wert für die MSBuild-Eigenschaft `TargetFramework` mit `netcoreapp` (z. B. `netcoreapp3.1` für Apps, die auf .NET Core 3.1 abzielen).</span><span class="sxs-lookup"><span data-stu-id="1a062-109">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="1a062-110">Ab NET 5.0 wird dieser Wert vereinfacht und beginnt nur mit `net` (z. B. `net5.0` für .NET 5.0).</span><span class="sxs-lookup"><span data-stu-id="1a062-110">Starting in .NET 5.0, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="1a062-111">Weitere Informationen finden Sie unter [Die Zukunft von .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) und [Zielframeworknamen in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="1a062-111">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="1a062-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="1a062-112">Reason for change</span></span>

- <span data-ttu-id="1a062-113">Dadurch wird der `TargetFramework`-Wert vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="1a062-113">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="1a062-114">Projekte können eine `TargetPlatform` in die `TargetFramework`-Eigenschaft einschließen.</span><span class="sxs-lookup"><span data-stu-id="1a062-114">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1a062-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="1a062-115">Recommended action</span></span>

<span data-ttu-id="1a062-116">Wenn Sie über Logik verfügen, die den Wert von `TargetFramework` analysiert, müssen Sie sie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1a062-116">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="1a062-117">Die folgende MSBuild-Bedingung basiert beispielsweise auf dem Wert von `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="1a062-117">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="1a062-118">Für diese Anforderung können Sie den Code so aktualisieren, dass er stattdessen den Zielframeworkbezeichner vergleicht.</span><span class="sxs-lookup"><span data-stu-id="1a062-118">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a><span data-ttu-id="1a062-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1a062-119">Affected APIs</span></span>

<span data-ttu-id="1a062-120">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="1a062-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
