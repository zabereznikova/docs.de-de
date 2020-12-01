---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032593"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="3ef76-101">Kestrel: Anforderungstrailer-Header wurden in neue Sammlung verschoben.</span><span class="sxs-lookup"><span data-stu-id="3ef76-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="3ef76-102">In früheren Versionen fügte Kestrel aufgeteilte HTTP/1.1-Trailer-Header in die Sammlung der Anforderungsheader ein, wenn der Anforderungstext bis zum Ende gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="3ef76-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="3ef76-103">Durch dieses Verhalten war keine eindeutige Trennung zwischen Headern und Trailern möglich.</span><span class="sxs-lookup"><span data-stu-id="3ef76-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="3ef76-104">Es wurde entschieden, die Trailer in eine neue Sammlung zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="3ef76-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="3ef76-105">HTTP/2-Anforderungstrailer waren in ASP.NET Core 2.2 nicht verfügbar. Sie sind jetzt aber in dieser neuen Sammlung in ASP.NET Core 3.0 enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ef76-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="3ef76-106">Für den Zugriff auf diese Trailer wurden neue Anforderungserweiterungsmethoden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3ef76-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="3ef76-107">HTTP/1.1-Trailer sind verfügbar, sobald der gesamte Anforderungstext gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="3ef76-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="3ef76-108">HTTP/2-Trailer sind verfügbar, sobald sie vom Client empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="3ef76-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="3ef76-109">Der Client sendet die Trailer erst, wenn der gesamte Anforderungstext mindestens vom Server gepuffert wurde.</span><span class="sxs-lookup"><span data-stu-id="3ef76-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="3ef76-110">Sie müssen möglicherweise den Anforderungstext lesen, um Pufferspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="3ef76-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="3ef76-111">Trailer sind immer verfügbar, wenn Sie den Anforderungstext bis zum Ende lesen.</span><span class="sxs-lookup"><span data-stu-id="3ef76-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="3ef76-112">Die Trailer markieren das Ende des Texts.</span><span class="sxs-lookup"><span data-stu-id="3ef76-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3ef76-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3ef76-113">Version introduced</span></span>

<span data-ttu-id="3ef76-114">3.0</span><span class="sxs-lookup"><span data-stu-id="3ef76-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3ef76-115">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="3ef76-115">Old behavior</span></span>

<span data-ttu-id="3ef76-116">Anforderungstrailer-Header wurden der Sammlung `HttpRequest.Headers` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3ef76-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3ef76-117">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="3ef76-117">New behavior</span></span>

<span data-ttu-id="3ef76-118">Anforderungstrailer-Header sind **nicht** in der Sammlung `HttpRequest.Headers` enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ef76-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="3ef76-119">Verwenden Sie die folgenden Erweiterungsmethoden in `HttpRequest`, um darauf zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="3ef76-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="3ef76-120">`GetDeclaredTrailers()` ruft den Anforderungsheader „Trailer“ ab, in dem aufgelistet wird, welche Trailer nach dem Text erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="3ef76-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="3ef76-121">`SupportsTrailers()` gibt an, ob die Anforderung das Empfangen von Trailer-Headern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3ef76-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="3ef76-122">`CheckTrailersAvailable()` legt fest, ob die Anforderung Trailer unterstützt und ob diese zum Lesen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3ef76-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="3ef76-123">`GetTrailer(string trailerName)` ruft den angeforderten Trailer-Header aus der Antwort ab.</span><span class="sxs-lookup"><span data-stu-id="3ef76-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3ef76-124">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="3ef76-124">Reason for change</span></span>

<span data-ttu-id="3ef76-125">Trailer stellen ein wichtiges Feature in Szenarien wie gRPC dar.</span><span class="sxs-lookup"><span data-stu-id="3ef76-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="3ef76-126">Das Zusammenführen der Trailer mit den Anforderungsheadern war für Benutzer verwirrend.</span><span class="sxs-lookup"><span data-stu-id="3ef76-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3ef76-127">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3ef76-127">Recommended action</span></span>

<span data-ttu-id="3ef76-128">Verwenden Sie die trailerbezogenen Erweiterungsmethoden in `HttpRequest`, um auf Trailer zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3ef76-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="3ef76-129">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3ef76-129">Category</span></span>

<span data-ttu-id="3ef76-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3ef76-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3ef76-131">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3ef76-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
