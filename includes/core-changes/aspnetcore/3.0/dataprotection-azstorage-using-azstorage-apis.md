---
ms.openlocfilehash: f103c96588bae167216d09a82973a4a7abfb5cc3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394036"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="c0f8f-101">Schutz von Daten: DataProtection.AzureStorage verwendet neue Azure Storage-APIs.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="c0f8f-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> hängt von den [Azure Storage-Bibliotheken](https://github.com/Azure/azure-storage-net) ab.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="c0f8f-103">Für diese Bibliotheken wurden die Assemblys, Pakete und Namespaces umbenannt.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="c0f8f-104">Ab ASP.NET Core 3.0 verwendet `Microsoft.AspNetCore.DataProtection.AzureStorage` die neuen APIs und Pakete mit dem Präfix `Microsoft.Azure.Storage.`.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="c0f8f-105">Wenn Sie Fragen zu den Azure Storage-APIs haben, lesen Sie unter <https://github.com/Azure/azure-storage-net> nach.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="c0f8f-106">Weitere Informationen finden Sie unter [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).</span><span class="sxs-lookup"><span data-stu-id="c0f8f-106">For discussion on this issue, see [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c0f8f-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c0f8f-107">Version introduced</span></span>

<span data-ttu-id="c0f8f-108">3.0</span><span class="sxs-lookup"><span data-stu-id="c0f8f-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c0f8f-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="c0f8f-109">Old behavior</span></span>

<span data-ttu-id="c0f8f-110">Das Paket verwies auf das NuGet-Paket `WindowsAzure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c0f8f-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="c0f8f-111">New behavior</span></span>

<span data-ttu-id="c0f8f-112">Das Pakete verweist auf das NuGet-Paket `Microsoft.Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c0f8f-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="c0f8f-113">Reason for change</span></span>

<span data-ttu-id="c0f8f-114">Diese Änderung ermöglicht `Microsoft.AspNetCore.DataProtection.AzureStorage` die Migration zu den empfohlenen Azure Storage-Paketen.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c0f8f-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="c0f8f-115">Recommended action</span></span>

<span data-ttu-id="c0f8f-116">Wenn Sie weiterhin die älteren Azure Storage-APIs mit ASP.NET Core 3.0 verwenden müssen, fügen Sie eine direkte Abhängigkeit vom Paket [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="c0f8f-117">Dieses Paket kann parallel zu den neuen `Microsoft.Azure.Storage`-APIs installiert werden.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="c0f8f-118">In vielen Fällen umfasst das Upgrade nur das Ändern der `using`-Anweisungen, um die neuen Namespaces zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="c0f8f-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="c0f8f-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="c0f8f-119">Category</span></span>

<span data-ttu-id="c0f8f-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0f8f-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c0f8f-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c0f8f-121">Affected APIs</span></span>

<span data-ttu-id="c0f8f-122">Keine</span><span class="sxs-lookup"><span data-stu-id="c0f8f-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
