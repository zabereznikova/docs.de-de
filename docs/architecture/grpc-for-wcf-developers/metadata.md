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
# <a name="metadata"></a>Metadaten

"Metadata" bezieht sich auf zusätzliche Daten, die während der Verarbeitung von Anforderungen und Antworten nützlich sein können, aber nicht Teil der eigentlichen Anwendungsdaten sind. Metadaten können Authentifizierungs Token, Anforderungs Bezeichner und Tags zu Überwachungszwecken oder Informationen zu den Daten enthalten, wie z. b. die Anzahl der Datensätze in einem DataSet.

Es ist möglich, WCF-Nachrichten mithilfe einer <xref:System.ServiceModel.OperationContextScope> und der <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType>-Eigenschaft generische Schlüssel-Wert-Header hinzuzufügen und diese mithilfe <xref:System.ServiceModel.Channels.MessageProperties>zu behandeln.

GrpC-Aufrufe und-Antworten können auch Metadaten enthalten, die den HTTP-Headern ähneln. Diese sind größtenteils für GrpC selbst unsichtbar und werden durchlaufen, um von Ihrem Anwendungscode oder von der Middleware verarbeitet zu werden. Metadaten werden als Schlüssel-Wert-Paare dargestellt, wobei der Schlüssel eine Zeichenfolge ist und der Wert entweder eine Zeichenfolge oder Binärdaten ist. Sie müssen keine Metadaten in der `.proto`-Datei angeben.

Metadaten werden mithilfe der `Metadata`-Klasse aus dem nuget-Paket " [GrpC. Core. API](https://www.nuget.org/packages/Grpc.Core.Api/) " verarbeitet. Diese Klasse kann mit der sammlungsinitialisierersyntax verwendet werden.

Im folgenden Beispiel wird gezeigt, wie einem- C# Client Metadaten hinzugefügt werden:

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
