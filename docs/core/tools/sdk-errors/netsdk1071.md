---
title: 'NETSDK1071: In einem PackageReference-Verweis auf „{0}“ wurde eine Version von `{1}` angegeben.'
description: Hier erfahren Sie, wie Sie das Problem eines PackageReference-Verweises auf ein Metapaket lösen, das im Framework mit einer Version eingeschlossen ist.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 852232cba04bb93a17872280e10848c2896991ae
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445678"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a><span data-ttu-id="55d09-103">NETSDK1071: Explizit versionierte PackageReference-Verweise auf ein Metapaket würden in das Framework eingeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="55d09-103">NETSDK1071: Explicitly versioned PackageReference to a metapackage that would be included with the framework.</span></span>

<span data-ttu-id="55d09-104">**Dieser Artikel gilt für:** ✔️ .NET 5.0.100 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="55d09-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="55d09-105">Wenn das .NET SDK die Warnung NETSDK1071 ausgibt, deutet dies darauf hin, dass es in der Zukunft möglicherweise einen Versionskonflikt zwischen der Version des Metapakets, wie es in einem PackageReference-Verweis angegeben ist, und der Version des Metapakets, wie auf es implizit über eine TargetFramework-Eigenschaft verwiesen wird, geben könnte:</span><span class="sxs-lookup"><span data-stu-id="55d09-105">When the .NET SDK issues warning NETSDK1071, it suggests there may be a version conflict in the future between the version of a metapackage specified in a PackageReference and the version of that metapackage as implicitly referenced via a TargetFramework property:</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="55d09-106">Da TargetFramework automatisch eine Version des Metapakets einführt, kommt es zu einem Konflikt zwischen den Versionen, sollten sich diese jemals unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="55d09-106">Since the TargetFramework automatically brings in a version of the metapackage, the versions will conflict should they ever differ.</span></span>

<span data-ttu-id="55d09-107">Problembehebung:</span><span class="sxs-lookup"><span data-stu-id="55d09-107">To resolve this:</span></span>

1. <span data-ttu-id="55d09-108">Wenn Sie .NET Core oder .NET Standard als Ziel verwenden, sollten Sie dies berücksichtigen und explizite Verweise auf `Microsoft.NETCore.App` oder `NETStandard.Library` in Ihrer Projektdatei vermeiden.</span><span class="sxs-lookup"><span data-stu-id="55d09-108">Consider, when targeting .NET Core or .NET Standard, avoiding explicit references to `Microsoft.NETCore.App` or `NETStandard.Library` in your project file.</span></span>
2. <span data-ttu-id="55d09-109">Wenn Sie .NET Core als Ziel verwenden und eine bestimmte Version der Runtime benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft verwenden, anstatt direkt auf Metapakete zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="55d09-109">If you need a specific version of the runtime when targeting .NET Core, use the `<RuntimeFrameworkVersion>`property instead of referencing the metapackage directly.</span></span> <span data-ttu-id="55d09-110">Dies kann beispielsweise vorkommen, wenn Sie [eigenständige Bereitstellungen](../../deploying/index.md#publish-self-contained) verwenden und eine bestimmte Patchversion der 1.0.0 LTS-Runtime benötigen.</span><span class="sxs-lookup"><span data-stu-id="55d09-110">As an example, this could happen if you're using [self-contained deployments](../../deploying/index.md#publish-self-contained) and need a specific patch of the 1.0.0 LTS runtime.</span></span>
3. <span data-ttu-id="55d09-111">Wenn Sie .NET Standard als Ziel verwenden und eine bestimmte Version von `NetStandard.Library` benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="55d09-111">If you need a specific version of `NetStandard.Library` when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set it to the version you need.</span></span>
4. <span data-ttu-id="55d09-112">Fügen Sie `Microsoft.NETCore.App` oder `NETSTandard.Library` in .NET Framework-Projekten nicht explizit Verweise hinzu, und aktualisieren Sie diese auch nicht.</span><span class="sxs-lookup"><span data-stu-id="55d09-112">Don't eplicitly add or update references to either `Microsoft.NETCore.App` or `NETSTandard.Library` in .NET Framework projects.</span></span> <span data-ttu-id="55d09-113">Wenn bei der Verwendung eines auf .NET Standard basierenden NuGet-Pakets eine bestimmte Version von `NETStandard.Library` benötigt wird, installiert NuGet diese automatisch.</span><span class="sxs-lookup"><span data-stu-id="55d09-113">NuGet automatically installs any version of `NETStandard.Library` you need when using a .NET Standard-based NuGet package.</span></span>
5. <span data-ttu-id="55d09-114">Geben Sie keine Version für `Microsoft.AspNetCore.App` oder `Microsoft.AspNetCore.All` an, wenn Sie .NET Core 2.1 oder höher verwenden, da das .NET Core SDK die benötigte Version automatisch auswählt.</span><span class="sxs-lookup"><span data-stu-id="55d09-114">Do not specify a version for `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` when using .NET Core 2.1+, as the .NET Core SDK automatically selects the appropriate version.</span></span> <span data-ttu-id="55d09-115">(Hinweis: Wenn .NET Core 2.1 als Ziel verwendet wird, funktioniert dies nur, wenn das Projekt auch `Microsoft.NET.Sdk.Web` verwendet.</span><span class="sxs-lookup"><span data-stu-id="55d09-115">(Note: This only works when targeting .NET Core 2.1 if the project also uses `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="55d09-116">Dieses Problem wurde im .NET Core 2.2 SDK gelöst.)</span><span class="sxs-lookup"><span data-stu-id="55d09-116">This problem was resolved in the .NET Core 2.2 SDK.)</span></span>
6. <span data-ttu-id="55d09-117">Wenn die Warnung nicht mehr angezeigt werden soll, können Sie sie deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="55d09-117">If you want the warning to go away, you can also disable it:</span></span>

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
