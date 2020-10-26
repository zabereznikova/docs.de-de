---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159487"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="a2f1e-101">TargetFramework-Änderung von „netcoreapp“ in „net“</span><span class="sxs-lookup"><span data-stu-id="a2f1e-101">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="a2f1e-102">Der Wert der MSBuild-Eigenschaft `TargetFramework` wurde von `netcoreapp3.1` in `net5.0` geändert.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-102">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="a2f1e-103">Dadurch wird möglicherweise Code unterbrochen, der von der Verarbeitung des Werts von `TargetFramework` abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-103">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a2f1e-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a2f1e-104">Version introduced</span></span>

<span data-ttu-id="a2f1e-105">5.0</span><span class="sxs-lookup"><span data-stu-id="a2f1e-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="a2f1e-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a2f1e-106">Change description</span></span>

<span data-ttu-id="a2f1e-107">In .NET Core 1.0 bis 3.1 beginnt der Wert für die MSBuild-Eigenschaft `TargetFramework` mit `netcoreapp` (z. B. `netcoreapp3.1` für Apps, die auf .NET Core 3.1 abzielen).</span><span class="sxs-lookup"><span data-stu-id="a2f1e-107">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="a2f1e-108">Ab NET 5.0 wird dieser Wert vereinfacht und beginnt nur mit `net` (z. B. `net5.0` für .NET 5.0).</span><span class="sxs-lookup"><span data-stu-id="a2f1e-108">Starting in .NET 5.0, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="a2f1e-109">Weitere Informationen finden Sie unter [Die Zukunft von .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) und [Zielframeworknamen in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="a2f1e-109">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a2f1e-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a2f1e-110">Reason for change</span></span>

- <span data-ttu-id="a2f1e-111">Dadurch wird der `TargetFramework`-Wert vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-111">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="a2f1e-112">Projekte können eine `TargetPlatform` in die `TargetFramework`-Eigenschaft einschließen.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-112">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a2f1e-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a2f1e-113">Recommended action</span></span>

<span data-ttu-id="a2f1e-114">Wenn Sie über Logik verfügen, die den Wert von `TargetFramework` analysiert, müssen Sie sie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-114">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="a2f1e-115">Die folgende MSBuild-Bedingung basiert beispielsweise auf dem Wert von `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-115">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="a2f1e-116">Für diese Anforderung können Sie den Code so aktualisieren, dass er stattdessen den Zielframeworkbezeichner vergleicht.</span><span class="sxs-lookup"><span data-stu-id="a2f1e-116">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a><span data-ttu-id="a2f1e-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a2f1e-117">Category</span></span>

<span data-ttu-id="a2f1e-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="a2f1e-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a2f1e-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a2f1e-119">Affected APIs</span></span>

<span data-ttu-id="a2f1e-120">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a2f1e-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
