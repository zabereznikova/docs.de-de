---
ms.openlocfilehash: 17a167e5245914329195d61ab45ae2d8ecb617d6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416278"
---
### <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="56f93-101">Blazor: Das Zielframework von NuGet-Paketen wurde geändert</span><span class="sxs-lookup"><span data-stu-id="56f93-101">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="56f93-102">Blazor 3.2-WebAssembly-Projekte wurden mit .NET Standard 2.1 als Ziel kompiliert (`<TargetFramework>netstandard2.1</TargetFramework>`).</span><span class="sxs-lookup"><span data-stu-id="56f93-102">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="56f93-103">In ASP.NET Core 5.0 verwenden sowohl Blazor Server- als auch Blazor-WebAssembly-Projekte .NET 5.0 als Ziel (`<TargetFramework>net5.0</TargetFramework>`).</span><span class="sxs-lookup"><span data-stu-id="56f93-103">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="56f93-104">Für eine besser Anpassung an die Änderung des Zielframeworks verwenden die folgenden Blazor-Pakete nicht mehr .NET Standard 2.1 als Ziel:</span><span class="sxs-lookup"><span data-stu-id="56f93-104">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* [<span data-ttu-id="56f93-105">Microsoft.AspNetCore.Components</span><span class="sxs-lookup"><span data-stu-id="56f93-105">Microsoft.AspNetCore.Components</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [<span data-ttu-id="56f93-106">Microsoft.AspNetCore.Components.Authorization</span><span class="sxs-lookup"><span data-stu-id="56f93-106">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="56f93-107">Microsoft.AspNetCore.Components.Forms</span><span class="sxs-lookup"><span data-stu-id="56f93-107">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [<span data-ttu-id="56f93-108">Microsoft.AspNetCore.Components.Web</span><span class="sxs-lookup"><span data-stu-id="56f93-108">Microsoft.AspNetCore.Components.Web</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [<span data-ttu-id="56f93-109">Microsoft.AspNetCore.Components.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="56f93-109">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="56f93-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span><span class="sxs-lookup"><span data-stu-id="56f93-110">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="56f93-111">Microsoft.JSInterop</span><span class="sxs-lookup"><span data-stu-id="56f93-111">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="56f93-112">Microsoft.JSInterop.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="56f93-112">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="56f93-113">Microsoft.Authentication.WebAssembly.Msal</span><span class="sxs-lookup"><span data-stu-id="56f93-113">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="56f93-114">Weitere Informationen finden Sie unter dem GitHub-Issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span><span class="sxs-lookup"><span data-stu-id="56f93-114">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="56f93-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="56f93-115">Version introduced</span></span>

<span data-ttu-id="56f93-116">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="56f93-116">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="56f93-117">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="56f93-117">Old behavior</span></span>

<span data-ttu-id="56f93-118">In Blazor 3.1 und 3.2 verwenden Pakete .NET Standard 2.1 und .NET Core 3.1 als Ziel.</span><span class="sxs-lookup"><span data-stu-id="56f93-118">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="56f93-119">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="56f93-119">New behavior</span></span>

<span data-ttu-id="56f93-120">In ASP.NET Core 5.0 verwenden Pakete .NET 5.0 als Ziel.</span><span class="sxs-lookup"><span data-stu-id="56f93-120">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="56f93-121">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="56f93-121">Reason for change</span></span>

<span data-ttu-id="56f93-122">Diese Änderung wurde vorgenommen, um eine besser Anpassung an die .NET-Zielframeworkanforderungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="56f93-122">The change was made to better align with .NET target framework requirements.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="56f93-123">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="56f93-123">Recommended action</span></span>

<span data-ttu-id="56f93-124">Blazor 3.2-WebAssembly-Projekte sollten .NET 5.0 als Ziel verwenden, wenn ihre Paketverweise auf 5.xx aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="56f93-124">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="56f93-125">Bibliotheken, die auf eines dieser Pakete verweisen, können je nach Anforderungen entweder .NET 5.0 oder mehrere Ziele als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="56f93-125">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

#### <a name="category"></a><span data-ttu-id="56f93-126">Kategorie</span><span class="sxs-lookup"><span data-stu-id="56f93-126">Category</span></span>

<span data-ttu-id="56f93-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="56f93-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="56f93-128">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="56f93-128">Affected APIs</span></span>

<span data-ttu-id="56f93-129">Keine</span><span class="sxs-lookup"><span data-stu-id="56f93-129">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
