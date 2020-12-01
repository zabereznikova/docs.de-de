---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032576"
---
### <a name="kestrel-connection-adapters-removed"></a><span data-ttu-id="5893b-101">Kestrel: Verbindungsadapter entfernt</span><span class="sxs-lookup"><span data-stu-id="5893b-101">Kestrel: Connection adapters removed</span></span>

<span data-ttu-id="5893b-102">Als Teil der Umstellung von „pubternal“-APIs zu `public` wurde das Konzept eines `IConnectionAdapter` aus Kestrel entfernt.</span><span class="sxs-lookup"><span data-stu-id="5893b-102">As part of the move to move "pubternal" APIs to `public`, the concept of an `IConnectionAdapter` was removed from Kestrel.</span></span> <span data-ttu-id="5893b-103">Verbindungsadapter wurden durch Verbindungsmiddleware ersetzt. Diese ähnelt der HTTP-Middleware in der ASP.NET Core-Pipeline, ist aber für Verbindungen auf niedrigerer Ebene konzipiert.</span><span class="sxs-lookup"><span data-stu-id="5893b-103">Connection adapters are being replaced with connection middleware (similar to HTTP middleware in the ASP.NET Core pipeline, but for lower-level connections).</span></span> <span data-ttu-id="5893b-104">Die HTTPS- und Verbindungsprotokollierung wurden von den Verbindungsadaptern zur Verbindungsmiddleware verschoben.</span><span class="sxs-lookup"><span data-stu-id="5893b-104">HTTPS and connection logging have moved from connection adapters to connection middleware.</span></span> <span data-ttu-id="5893b-105">Diese Erweiterungsmethoden sollten weiterhin nahtlos funktionieren, aber die Implementierungsdetails wurden geändert.</span><span class="sxs-lookup"><span data-stu-id="5893b-105">Those extension methods should continue to work seamlessly, but the implementation details have changed.</span></span>

<span data-ttu-id="5893b-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412).</span><span class="sxs-lookup"><span data-stu-id="5893b-106">For more information, see [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412).</span></span> <span data-ttu-id="5893b-107">Weitere Informationen finden Sie unter [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).</span><span class="sxs-lookup"><span data-stu-id="5893b-107">For discussion, see [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5893b-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5893b-108">Version introduced</span></span>

<span data-ttu-id="5893b-109">3.0</span><span class="sxs-lookup"><span data-stu-id="5893b-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="5893b-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="5893b-110">Old behavior</span></span>

<span data-ttu-id="5893b-111">Kestrel-Erweiterbarkeitskomponenten wurden mit `IConnectionAdapter` erstellt.</span><span class="sxs-lookup"><span data-stu-id="5893b-111">Kestrel extensibility components were created using `IConnectionAdapter`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="5893b-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="5893b-112">New behavior</span></span>

<span data-ttu-id="5893b-113">Kestrel-Erweiterbarkeitskomponenten werden als [Middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f) erstellt.</span><span class="sxs-lookup"><span data-stu-id="5893b-113">Kestrel extensibility components are created as [middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5893b-114">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="5893b-114">Reason for change</span></span>

<span data-ttu-id="5893b-115">Mit dieser Änderung soll eine flexiblere Erweiterbarkeitsarchitektur bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5893b-115">This change is intended to provide a more flexible extensibility architecture.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5893b-116">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5893b-116">Recommended action</span></span>

<span data-ttu-id="5893b-117">Stellen Sie alle Implementierungen von `IConnectionAdapter` wie [hier](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f) gezeigt auf das neue Middlewarekonzept um.</span><span class="sxs-lookup"><span data-stu-id="5893b-117">Convert any implementations of `IConnectionAdapter` to use the new middleware pattern as shown [here](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="category"></a><span data-ttu-id="5893b-118">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5893b-118">Category</span></span>

<span data-ttu-id="5893b-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5893b-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5893b-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5893b-120">Affected APIs</span></span>

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
