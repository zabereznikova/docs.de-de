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
# <a name="metadata"></a>Metadaten

*Metadaten* beziehen sich auf zusätzliche Daten, die während der Verarbeitung von Anforderungen und Antworten nützlich sein können, aber nicht Teil der eigentlichen Anwendungsdaten sind. Metadaten können Authentifizierungs Token, Anforderungs Bezeichner und Tags zu Überwachungszwecken sowie Informationen zu den Daten enthalten, wie z. b. die Anzahl der Datensätze in einem DataSet.

Es ist möglich, Windows Communication Foundation (WCF)-Nachrichten generische Schlüssel-Wert-Header hinzuzufügen, indem Sie eine <xref:System.ServiceModel.OperationContextScope> und die <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType>-Eigenschaft verwenden und diese mithilfe von <xref:System.ServiceModel.Channels.MessageProperties>verarbeiten.

GrpC-Aufrufe und-Antworten können auch Metadaten enthalten, die mit HTTP-Headern vergleichbar sind. Diese Metadaten sind größtenteils für GrpC selbst unsichtbar und werden durchlaufen, um von Ihrem Anwendungscode oder von der Middleware verarbeitet zu werden. Metadaten werden als Schlüssel-Wert-Paare dargestellt, wobei der Schlüssel eine Zeichenfolge ist und der Wert entweder eine Zeichenfolge oder Binärdaten ist. Sie müssen keine Metadaten in der `.proto`-Datei angeben.

Metadaten werden von der `Metadata`-Klasse des nuget-Pakets " [GrpC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) " verarbeitet. Diese Klasse kann mit der sammlungsinitialisierersyntax verwendet werden.

In diesem Beispiel wird gezeigt, wie einem- C# Client Metadaten hinzugefügt werden:

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

GrpC-Dienste können über die `RequestHeaders`-Eigenschaft des `ServerCallContext` Arguments auf Metadaten zugreifen:

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

Dienste können mithilfe der `ResponseTrailers`-Eigenschaft von `ServerCallContext`Metadaten an Clients senden:

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
>[Zurück](rpc-types.md)
>[Weiter](error-handling.md)
