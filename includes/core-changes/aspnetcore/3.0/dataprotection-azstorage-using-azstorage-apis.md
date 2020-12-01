---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032496"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a><span data-ttu-id="11530-101">Schutz von Daten: DataProtection.Blobs verwendet neue Azure Storage-APIs</span><span class="sxs-lookup"><span data-stu-id="11530-101">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>

<span data-ttu-id="11530-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` hängt von den [Azure Storage-Bibliotheken](https://github.com/Azure/azure-storage-net) ab.</span><span class="sxs-lookup"><span data-stu-id="11530-102">`Azure.Extensions.AspNetCore.DataProtection.Blobs` depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="11530-103">Für diese Bibliotheken wurden die Assemblys, Pakete und Namespaces umbenannt.</span><span class="sxs-lookup"><span data-stu-id="11530-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="11530-104">Ab ASP.NET Core 3.0 verwendet `Azure.Extensions.AspNetCore.DataProtection.Blobs` die neuen APIs und Pakete mit dem Präfix `Azure.Storage.`.</span><span class="sxs-lookup"><span data-stu-id="11530-104">Starting in ASP.NET Core 3.0, `Azure.Extensions.AspNetCore.DataProtection.Blobs` uses the new `Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="11530-105">Wenn Sie Fragen zu den Azure Storage-APIs haben, lesen Sie unter <https://github.com/Azure/azure-storage-net> nach.</span><span class="sxs-lookup"><span data-stu-id="11530-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="11530-106">Dieses Problem wird unter [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570) behandelt.</span><span class="sxs-lookup"><span data-stu-id="11530-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="11530-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="11530-107">Version introduced</span></span>

<span data-ttu-id="11530-108">3.0</span><span class="sxs-lookup"><span data-stu-id="11530-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="11530-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="11530-109">Old behavior</span></span>

<span data-ttu-id="11530-110">Das Paket verwies auf das NuGet-Paket `WindowsAzure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="11530-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>
<span data-ttu-id="11530-111">Das Pakete verweist auf das NuGet-Paket `Microsoft.Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="11530-111">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="11530-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="11530-112">New behavior</span></span>

<span data-ttu-id="11530-113">Das Pakete verweist auf das NuGet-Paket `Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="11530-113">The package references the `Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="11530-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="11530-114">Reason for change</span></span>

<span data-ttu-id="11530-115">Diese Änderung ermöglicht `Azure.Extensions.AspNetCore.DataProtection.Blobs` die Migration zu den empfohlenen Azure Storage-Paketen.</span><span class="sxs-lookup"><span data-stu-id="11530-115">This change allows `Azure.Extensions.AspNetCore.DataProtection.Blobs` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="11530-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="11530-116">Recommended action</span></span>

<span data-ttu-id="11530-117">Wenn Sie weiterhin die älteren Azure Storage-APIs mit ASP.NET Core 3.0 verwenden müssen, fügen Sie eine direkte Abhängigkeit vom Paket [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) oder [Microsoft Azure Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/) hinzu.</span><span class="sxs-lookup"><span data-stu-id="11530-117">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the package [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) or [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/).</span></span> <span data-ttu-id="11530-118">Dieses Paket kann parallel zu den neuen `Azure.Storage`-APIs installiert werden.</span><span class="sxs-lookup"><span data-stu-id="11530-118">This package can be installed alongside the new `Azure.Storage` APIs.</span></span>

<span data-ttu-id="11530-119">In vielen Fällen umfasst das Upgrade nur das Ändern der `using`-Anweisungen, um die neuen Namespaces zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="11530-119">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a><span data-ttu-id="11530-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="11530-120">Category</span></span>

<span data-ttu-id="11530-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="11530-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="11530-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="11530-122">Affected APIs</span></span>

<span data-ttu-id="11530-123">Keine</span><span class="sxs-lookup"><span data-stu-id="11530-123">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
