---
title: 'Metadaten: GrpC für WCF-Entwickler'
description: Verwendung von Metadaten in GrpC, um zusätzlichen Kontext zwischen Clients und Servern zu übergeben
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 32559b3404b12f366fc1624299d04cff9faad9d6
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841582"
---
# <a name="metadata"></a><span data-ttu-id="63721-103">Metadaten</span><span class="sxs-lookup"><span data-stu-id="63721-103">Metadata</span></span>

<span data-ttu-id="63721-104">"Metadata" bezieht sich auf zusätzliche Daten, die während der Verarbeitung von Anforderungen und Antworten nützlich sein können, aber nicht Teil der eigentlichen Anwendungsdaten sind.</span><span class="sxs-lookup"><span data-stu-id="63721-104">"Metadata" refers to additional data that may be useful while processing requests and responses but is not part of the actual application data.</span></span> <span data-ttu-id="63721-105">Metadaten können Authentifizierungs Token, Anforderungs Bezeichner und Tags zu Überwachungszwecken oder Informationen zu den Daten enthalten, wie z. b. die Anzahl der Datensätze in einem DataSet.</span><span class="sxs-lookup"><span data-stu-id="63721-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, or information about the data like the number of records in a dataset.</span></span>

<span data-ttu-id="63721-106">Es ist möglich, WCF-Nachrichten mithilfe einer <xref:System.ServiceModel.OperationContextScope> und der <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType>-Eigenschaft generische Schlüssel-Wert-Header hinzuzufügen und diese mithilfe <xref:System.ServiceModel.Channels.MessageProperties>zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="63721-106">It's possible to add generic key/value headers to WCF messages using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property, and handle them using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="63721-107">GrpC-Aufrufe und-Antworten können auch Metadaten enthalten, die den HTTP-Headern ähneln.</span><span class="sxs-lookup"><span data-stu-id="63721-107">gRPC calls and responses can also include metadata similar to HTTP headers.</span></span> <span data-ttu-id="63721-108">Diese sind größtenteils für GrpC selbst unsichtbar und werden durchlaufen, um von Ihrem Anwendungscode oder von der Middleware verarbeitet zu werden.</span><span class="sxs-lookup"><span data-stu-id="63721-108">These are mostly invisible to gRPC itself and are passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="63721-109">Metadaten werden als Schlüssel-Wert-Paare dargestellt, wobei der Schlüssel eine Zeichenfolge ist und der Wert entweder eine Zeichenfolge oder Binärdaten ist.</span><span class="sxs-lookup"><span data-stu-id="63721-109">Metadata is represented as key/value pairs where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="63721-110">Sie müssen keine Metadaten in der `.proto`-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="63721-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="63721-111">Metadaten werden mithilfe der `Metadata`-Klasse aus dem nuget-Paket " [GrpC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) " verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="63721-111">Metadata is handled using the `Metadata` class from the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="63721-112">Diese Klasse kann mit der sammlungsinitialisierersyntax verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63721-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="63721-113">Im folgenden Beispiel wird gezeigt, wie einem- C# Client Metadaten hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="63721-113">The following example shows how to add metadata to a call from a C# client:</span></span>

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

<span data-ttu-id="63721-114">GrpC-Dienste können über die `RequestHeaders`-Eigenschaft des `ServerCallContext` Arguments auf Metadaten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="63721-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

<span data-ttu-id="63721-115">Dienste können mithilfe der `ResponseTrailers`-Eigenschaft von `ServerCallContext`Metadaten an Clients senden:</span><span class="sxs-lookup"><span data-stu-id="63721-115">Services can send metadata to clients using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="63721-116">[Zurück](rpc-types.md)
>[Weiter](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="63721-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
