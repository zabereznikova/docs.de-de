---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901986"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="8ba0d-101">Zwischenspeicherung: CompactOnMemoryPressure-Eigenschaft wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="8ba0d-102">Die [veralteten MemoryCacheOptions-APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) wurden im Release ASP.NET Core 3.0 entfernt.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="8ba0d-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8ba0d-103">Change description</span></span>

<span data-ttu-id="8ba0d-104">Diese Änderung resultiert aus [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span><span class="sxs-lookup"><span data-stu-id="8ba0d-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="8ba0d-105">Weitere Informationen finden Sie unter [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span><span class="sxs-lookup"><span data-stu-id="8ba0d-105">For discussion, see [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8ba0d-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8ba0d-106">Version introduced</span></span>

<span data-ttu-id="8ba0d-107">3.0</span><span class="sxs-lookup"><span data-stu-id="8ba0d-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8ba0d-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="8ba0d-108">Old behavior</span></span>

<span data-ttu-id="8ba0d-109">Die `MemoryCacheOptions.CompactOnMemoryPressure`-Eigenschaft war verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="8ba0d-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="8ba0d-110">New behavior</span></span>

<span data-ttu-id="8ba0d-111">Die `MemoryCacheOptions.CompactOnMemoryPressure`-Eigenschaft wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8ba0d-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="8ba0d-112">Reason for change</span></span>

<span data-ttu-id="8ba0d-113">Die automatische Komprimierung des Caches hat Probleme verursacht.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="8ba0d-114">Um unerwartetes Verhalten zu vermeiden, sollte der Cache nur bei Bedarf komprimiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8ba0d-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="8ba0d-115">Recommended action</span></span>

<span data-ttu-id="8ba0d-116">Um den Cache zu komprimieren, führen Sie eine Umwandlung in `MemoryCache` durch und rufen bei Bedarf `Compact` auf.</span><span class="sxs-lookup"><span data-stu-id="8ba0d-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="8ba0d-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8ba0d-117">Category</span></span>

<span data-ttu-id="8ba0d-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8ba0d-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8ba0d-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8ba0d-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
