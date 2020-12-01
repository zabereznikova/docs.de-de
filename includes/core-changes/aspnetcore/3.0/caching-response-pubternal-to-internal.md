---
ms.openlocfilehash: ae5a5fbf97ed4a03de7d35b9d5d5ca8de3aebc39
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032463"
---
### <a name="caching-responsecaching-pubternal-types-changed-to-internal"></a><span data-ttu-id="77a17-101">Zwischenspeicherung: „pubternal“-Typen in ResponseCaching in „internal“-Typen geändert</span><span class="sxs-lookup"><span data-stu-id="77a17-101">Caching: ResponseCaching "pubternal" types changed to internal</span></span>

<span data-ttu-id="77a17-102">In ASP.NET Core 3.0 wurden „pubternal“-Typen in `ResponseCaching` in `internal` geändert.</span><span class="sxs-lookup"><span data-stu-id="77a17-102">In ASP.NET Core 3.0, "pubternal" types in `ResponseCaching` have been changed to `internal`.</span></span>

<span data-ttu-id="77a17-103">Außerdem werden die Standardimplementierungen von `IResponseCachingPolicyProvider` und `IResponseCachingKeyProvider` Diensten nicht mehr als Teil der `AddResponseCaching`-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="77a17-103">In addition, default implementations of `IResponseCachingPolicyProvider` and `IResponseCachingKeyProvider` are no longer added to services as part of the `AddResponseCaching` method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="77a17-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="77a17-104">Change description</span></span>

<span data-ttu-id="77a17-105">In ASP.NET Core werden „pubternal“-Typen als `public` deklariert, befinden sich jedoch in einem Namespace mit dem Suffix `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="77a17-105">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a namespace suffixed with `.Internal`.</span></span> <span data-ttu-id="77a17-106">Diese Typen sind zwar öffentlich („public“), sie verfügen jedoch nicht über eine Unterstützungsrichtlinie und können daher Breaking Changes unterliegen.</span><span class="sxs-lookup"><span data-stu-id="77a17-106">While these types are public, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="77a17-107">Da diese Typen leider relativ häufig versehentlich verwendet werden, können an diesen Projekten Breaking Changes auftreten, und die Fähigkeit zum Verwalten des Frameworks kann eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="77a17-107">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77a17-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="77a17-108">Version introduced</span></span>

<span data-ttu-id="77a17-109">3.0</span><span class="sxs-lookup"><span data-stu-id="77a17-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="77a17-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="77a17-110">Old behavior</span></span>

<span data-ttu-id="77a17-111">Diese Typen waren öffentlich sichtbar, wurden jedoch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="77a17-111">These types were publicly visible, but unsupported.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="77a17-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="77a17-112">New behavior</span></span>

<span data-ttu-id="77a17-113">Diese Typen sind jetzt `internal`.</span><span class="sxs-lookup"><span data-stu-id="77a17-113">These types are now `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="77a17-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="77a17-114">Reason for change</span></span>

<span data-ttu-id="77a17-115">Der Geltungsbereich `internal` entspricht besser der nicht unterstützten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="77a17-115">The `internal` scope better reflects the unsupported policy.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77a17-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="77a17-116">Recommended action</span></span>

<span data-ttu-id="77a17-117">Kopieren Sie Typen, die von Ihrer App oder Bibliothek verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77a17-117">Copy types that are used by your app or library.</span></span>

#### <a name="category"></a><span data-ttu-id="77a17-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="77a17-118">Category</span></span>

<span data-ttu-id="77a17-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="77a17-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77a17-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="77a17-120">Affected APIs</span></span>

- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- <xref:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.%23ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- `M:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)",
"nameWithType": "ResponseCachingMiddleware.ResponseCachingMiddleware(RequestDelegate, IOptions<ResponseCachingOptions>, ILoggerFactory, IResponseCachingPolicyProvider, IResponseCache, IResponseCachingKeyProvider)`

-->
