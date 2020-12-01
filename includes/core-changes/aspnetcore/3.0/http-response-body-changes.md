---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032543"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="b5f08-101">HTTP: Änderungen an der Infrastruktur von Antworttexten</span><span class="sxs-lookup"><span data-stu-id="b5f08-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="b5f08-102">Die Infrastruktur für HTTP-Antworttexte wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="b5f08-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="b5f08-103">Wenn Sie `HttpResponse` direkt verwenden, sollten keine Änderungen am Code erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="b5f08-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="b5f08-104">Wenn Sie `HttpResponse.Body` umschließen oder auf `HttpContext.Features` zugreifen, lesen Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="b5f08-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b5f08-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b5f08-105">Version introduced</span></span>

<span data-ttu-id="b5f08-106">3.0</span><span class="sxs-lookup"><span data-stu-id="b5f08-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b5f08-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="b5f08-107">Old behavior</span></span>

<span data-ttu-id="b5f08-108">Dem HTTP-Antworttext waren drei APIs zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="b5f08-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="b5f08-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="b5f08-109">New behavior</span></span>

<span data-ttu-id="b5f08-110">Wenn Sie `HttpResponse.Body` ersetzen, wird das gesamte `IHttpResponseBodyFeature` durch einen Wrapper um den angegebenen Stream ersetzt, indem `StreamResponseBodyFeature` verwendet wird, um Standardimplementierungen für alle erwarteten APIs bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5f08-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="b5f08-111">Durch das Zurücksetzen des ursprünglichen Streams wird diese Änderung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b5f08-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b5f08-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b5f08-112">Reason for change</span></span>

<span data-ttu-id="b5f08-113">Die Antworttext-APIs sollen in einer einzigen neuen Funktionsschnittstelle zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="b5f08-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b5f08-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="b5f08-114">Recommended action</span></span>

<span data-ttu-id="b5f08-115">Verwenden Sie `IHttpResponseBodyFeature` an den Stellen, an denen Sie zuvor `IHttpResponseFeature.Body`, `IHttpSendFileFeature` oder `IHttpBufferingFeature` verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="b5f08-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="b5f08-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b5f08-116">Category</span></span>

<span data-ttu-id="b5f08-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b5f08-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b5f08-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b5f08-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
