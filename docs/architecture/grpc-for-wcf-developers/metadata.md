---
title: 'Metadaten: GrpC für WCF-Entwickler'
description: Verwendung von Metadaten in GrpC, um zusätzlichen Kontext zwischen Clients und Servern zu übergeben.
ms.date: 09/02/2019
ms.openlocfilehash: 64fa94d1e63af480cbc7363631de161c5b8b8fb8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628578"
---
# <a name="metadata"></a><span data-ttu-id="3ae62-103">Metadaten</span><span class="sxs-lookup"><span data-stu-id="3ae62-103">Metadata</span></span>

<span data-ttu-id="3ae62-104">*Metadaten* beziehen sich auf zusätzliche Daten, die während der Verarbeitung von Anforderungen und Antworten nützlich sein können, aber nicht Teil der eigentlichen Anwendungsdaten sind.</span><span class="sxs-lookup"><span data-stu-id="3ae62-104">*Metadata* refers to additional data that might be useful during the processing of requests and responses but that’s not part of the actual application data.</span></span> <span data-ttu-id="3ae62-105">Metadaten können Authentifizierungs Token, Anforderungs Bezeichner und Tags zu Überwachungszwecken sowie Informationen zu den Daten enthalten, wie z. b. die Anzahl der Datensätze in einem DataSet.</span><span class="sxs-lookup"><span data-stu-id="3ae62-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, and information about the data, like the number of records in a dataset.</span></span>

<span data-ttu-id="3ae62-106">Es ist möglich, Windows Communication Foundation (WCF)-Nachrichten generische Schlüssel-Wert-Header hinzuzufügen, indem Sie eine <xref:System.ServiceModel.OperationContextScope> und die <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType>-Eigenschaft verwenden und diese mithilfe von <xref:System.ServiceModel.Channels.MessageProperties>verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3ae62-106">It's possible to add generic key/value headers to Windows Communication Foundation (WCF) messages by using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property and handle them by using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="3ae62-107">GrpC-Aufrufe und-Antworten können auch Metadaten enthalten, die mit HTTP-Headern vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="3ae62-107">gRPC calls and responses can also include metadata that's similar to HTTP headers.</span></span> <span data-ttu-id="3ae62-108">Diese Metadaten sind größtenteils für GrpC selbst unsichtbar und werden durchlaufen, um von Ihrem Anwendungscode oder von der Middleware verarbeitet zu werden.</span><span class="sxs-lookup"><span data-stu-id="3ae62-108">This metadata is mostly invisible to gRPC itself and is passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="3ae62-109">Metadaten werden als Schlüssel-Wert-Paare dargestellt, wobei der Schlüssel eine Zeichenfolge ist und der Wert entweder eine Zeichenfolge oder Binärdaten ist.</span><span class="sxs-lookup"><span data-stu-id="3ae62-109">Metadata is represented as key/value pairs, where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="3ae62-110">Sie müssen keine Metadaten in der `.proto`-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="3ae62-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="3ae62-111">Metadaten werden von der `Metadata`-Klasse des nuget-Pakets " [GrpC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) " verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="3ae62-111">Metadata is handled by the `Metadata` class of the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="3ae62-112">Diese Klasse kann mit der sammlungsinitialisierersyntax verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ae62-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="3ae62-113">In diesem Beispiel wird gezeigt, wie einem- C# Client Metadaten hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="3ae62-113">This example shows how to add metadata to a call from a C# client:</span></span>

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

<span data-ttu-id="3ae62-114">GrpC-Dienste können über die `RequestHeaders`-Eigenschaft des `ServerCallContext` Arguments auf Metadaten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="3ae62-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

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

<span data-ttu-id="3ae62-115">Dienste können mithilfe der `ResponseTrailers`-Eigenschaft von `ServerCallContext`Metadaten an Clients senden:</span><span class="sxs-lookup"><span data-stu-id="3ae62-115">Services can send metadata to clients by using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="3ae62-116">[Zurück](rpc-types.md)
>[Weiter](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="3ae62-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
