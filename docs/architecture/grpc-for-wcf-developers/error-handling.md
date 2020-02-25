---
title: 'Fehlerbehandlung: GrpC für WCF-Entwickler'
description: Themen in Bezug auf die Fehlerbehandlung in GrpC. Enthält eine Tabelle mit den am häufigsten verwendeten Statuscodes.
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542792"
---
# <a name="error-handling"></a>Fehlerbehandlung

Windows Communication Foundation (WCF) verwendet <xref:System.ServiceModel.FaultException%601> und " [fehlercontract](xref:System.ServiceModel.FaultContractAttribute) ", um ausführliche Fehlerinformationen bereitzustellen, einschließlich der Unterstützung des SOAP-Fehler Standards.

Leider fehlt in der aktuellen Version von GrpC die Komplexität, die mit WCF gefunden wurde, und Sie verfügt nur über eine begrenzte Integrierte Fehlerbehandlung, die auf einfachen Statuscodes und Metadaten basiert. In der folgenden Tabelle finden Sie eine kurze Anleitung zu den am häufigsten verwendeten Statuscodes:

| Statuscode | Problem |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Die Methode wurde nicht geschrieben. |
| `GRPC_STATUS_UNAVAILABLE` | Problem mit dem gesamten Dienst. |
| `GRPC_STATUS_UNKNOWN` | Ungültige Antwort. |
| `GRPC_STATUS_INTERNAL` | Problem beim Codieren/Decodieren. |
| `GRPC_STATUS_UNAUTHENTICATED` | Die Authentifizierung ist fehlgeschlagen. |
| `GRPC_STATUS_PERMISSION_DENIED` | Fehler bei der Autorisierung. |
| `GRPC_STATUS_CANCELLED` | Der Aufruf wurde abgebrochen, normalerweise durch den Aufrufer. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>Fehler in ASP.net Core GrpC

Ein ASP.net Core GrpC-Dienst kann eine Fehler Antwort senden, indem er eine `RpcException`auslöst, die vom Client abgefangen werden kann, als ob er sich im selben Prozess befindet. Der `RpcException` muss einen Statuscode und eine Beschreibung enthalten und optional Metadaten und eine längere Ausnahme Meldung enthalten. Die Metadaten können verwendet werden, um unterstützende Daten zu senden, ähnlich wie `FaultContract` Objekten zusätzliche Daten für WCF-Fehler enthalten können.

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

## <a name="catch-errors-in-grpc-clients"></a>Catch-Fehler in GrpC-Clients

Ebenso wie WCF-Clients <xref:System.ServiceModel.FaultException%601> Fehler erfassen können, kann ein GrpC-Client eine `RpcException` abfangen, um Fehler zu behandeln. Da `RpcException` kein generischer Typ ist, können Sie verschiedene Fehlertypen in unterschiedlichen Blöcken nicht erfassen. Sie können jedoch die C# *Ausnahme Filter* Funktion verwenden, um separate `catch` Blöcke für verschiedene Statuscodes zu deklarieren, wie im folgenden Beispiel gezeigt:

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

Google hat ein Umfang [reicheres Fehlermodell](https://cloud.google.com/apis/design/errors#error_model) entwickelt, das eher wie der WCF-Fehler [Vertrag](xref:System.ServiceModel.FaultContractAttribute), aber dieses Modell C# wird noch nicht unterstützt. Derzeit ist Sie nur für Go, Java, Python und C++verfügbar.

>[!div class="step-by-step"]
>[Zurück](metadata.md)
>[Weiter](ws-protocols.md)
