---
title: 'Fehlerbehandlung: GrpC für WCF-Entwickler'
description: ZU SCHREIBEND
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 91f5789d8ed0f01f3ce2f3f9a6c6ccf14f245290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73842002"
---
# <a name="error-handling"></a>Fehlerbehandlung

WCF verwendet `FaultException<T>` und `FaultContract`, um detaillierte Fehlerinformationen bereitzustellen, einschließlich der Unterstützung des SOAP-Fehler Standards.

Leider fehlt in der aktuellen Version von GrpC die Komplexität, die mit WCF gefunden wurde, und Sie verfügt nur über eine begrenzte Integrierte Fehlerbehandlung, die auf einfachen Statuscodes und Metadaten basiert. In der folgenden Tabelle finden Sie eine kurze Anleitung zu den am häufigsten verwendeten Statuscodes:

| Statuscode | Problem |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Die Methode wurde nicht geschrieben. |
| `GRPC_STATUS_UNAVAILABLE` | Problem mit dem gesamten Dienst. |
| `GRPC_STATUS_UNKNOWN` | Ungültige Antwort. |
| `GRPC_STATUS_INTERNAL` | Problem beim Codieren/Decodieren. |
| `GRPC_STATUS_UNAUTHENTICATED` | Fehler bei der Authentifizierung. |
| `GRPC_STATUS_PERMISSION_DENIED` | Autorisierungs Fehler. |
| `GRPC_STATUS_CANCELLED` | Der Aufruf wurde abgebrochen, normalerweise durch den Aufrufer. |

## <a name="raising-errors-in-aspnet-core-grpc"></a>Fehler beim Auftreten von Fehlern in ASP.net Core GrpC

Ein ASP.net Core GrpC-Dienst kann eine Fehler Antwort senden, indem er eine `RpcException`auslöst, die vom Client abgefangen werden kann, als ob er sich im selben Prozess befindet. Der `RpcException` muss einen Statuscode und eine Beschreibung enthalten und optional Metadaten und eine längere Ausnahme Meldung enthalten. Die Metadaten können verwendet werden, um unterstützende Daten zu senden, ähnlich wie `FaultContract` Objekten zusätzliche Daten für WCF-Fehler enthalten könnten.

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catching-errors-in-grpc-clients"></a>Abfangen von Fehlern in GrpC-Clients

Ebenso wie WCF-Clients <xref:System.ServiceModel.FaultException%601> Fehler erfassen können, kann ein GrpC-Client eine `RpcException` abfangen, um Fehler zu behandeln. Da `RpcException` kein generischer Typ ist, können Sie verschiedene Fehlertypen nicht in unterschiedlichen Blöcken erfassen, aber C#Sie können die *Ausnahme Filter* Funktion verwenden, um separate `catch` Blöcke für verschiedene Statuscodes zu deklarieren, wie im folgenden Beispiel gezeigt:

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> Wenn Sie zusätzliche Metadaten für Fehler bereitstellen, stellen Sie sicher, dass Sie die relevanten Schlüssel und Werte in der API-Dokumentation oder in Kommentaren in der `.proto`-Datei dokumentieren.

## <a name="grpc-richer-error-model"></a>umfangreicheres GrpC-Fehlermodell

In C# der Vorschau hat Google ein Umfang [reicheres Fehlermodell](https://cloud.google.com/apis/design/errors#error_model) [entwickelt, das besser wie der von](xref:System.ServiceModel.FaultContractAttribute)WCF ist, aber noch nicht unterstützt wird. Derzeit ist Sie nur für Go, Java, Python und C++verfügbar, aber die Unterstützung C# für wird im nächsten Jahr erwartet.

>[!div class="step-by-step"]
>[Zurück](metadata.md)
>[Weiter](ws-protocols.md)
