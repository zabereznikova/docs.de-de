---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032583"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="d86fe-101">Kestrel: Datentransportabstraktionen wurden entfernt und öffentlich gemacht.</span><span class="sxs-lookup"><span data-stu-id="d86fe-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="d86fe-102">Im Rahmen der Umstellung von „pubternal“-APIs werden die Kestrel-APIs auf der Datentransportschicht als öffentliche Schnittstelle in der `Microsoft.AspNetCore.Connections.Abstractions`-Bibliothek verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="d86fe-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d86fe-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d86fe-103">Version introduced</span></span>

<span data-ttu-id="d86fe-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d86fe-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d86fe-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="d86fe-105">Old behavior</span></span>

- <span data-ttu-id="d86fe-106">Abstraktionen zum Datentransport waren in der `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`-Bibliothek verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d86fe-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="d86fe-107">Die `ListenOptions.NoDelay`-Eigenschaft war verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d86fe-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d86fe-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="d86fe-108">New behavior</span></span>

- <span data-ttu-id="d86fe-109">Die `IConnectionListener`-Schnittstelle wurde in der `Microsoft.AspNetCore.Connections.Abstractions`-Bibliothek eingeführt, um die am häufigsten verwendeten Funktionen aus der `...Transport.Abstractions`-Bibliothek verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="d86fe-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="d86fe-110">`NoDelay` ist nun in den Datentransportoptionen (`LibuvTransportOptions` und `SocketTransportOptions`) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d86fe-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="d86fe-111">`SchedulingMode` ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d86fe-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d86fe-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="d86fe-112">Reason for change</span></span>

<span data-ttu-id="d86fe-113">In ASP.NET Core 3.0 werden keine „pubternal“-APIs mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="d86fe-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d86fe-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="d86fe-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="d86fe-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d86fe-115">Category</span></span>

<span data-ttu-id="d86fe-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d86fe-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d86fe-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d86fe-117">Affected APIs</span></span>

<span data-ttu-id="d86fe-118">Keine</span><span class="sxs-lookup"><span data-stu-id="d86fe-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
