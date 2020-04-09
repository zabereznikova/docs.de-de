---
title: Fehlerbehandlung - gRPC für WCF-Entwickler
description: Themen zur Fehlerbehandlung in gRPC. Enthält eine Tabelle mit den am häufigsten verwendeten Statuscodes.
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988946"
---
# <a name="error-handling"></a>Fehlerbehandlung

Windows Communication Foundation (WCF) verwendet <xref:System.ServiceModel.FaultException%601> und [FaultContract](xref:System.ServiceModel.FaultContractAttribute) verwendet, um detaillierte Fehlerinformationen bereitzustellen, einschließlich der Unterstützung des SOAP Fault-Standards.

Leider fehlt der aktuellen Version von gRPC die mit WCF gefundene Raffinesse und es gibt nur eine begrenzte integrierte Fehlerbehandlung basierend auf einfachen Statuscodes und Metadaten. Die folgende Tabelle enthält eine Kurzanleitung zu den am häufigsten verwendeten Statuscodes:

| Statuscode | Problem |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | Die Methode wurde nicht geschrieben. |
| `GRPC_STATUS_UNAVAILABLE` | Problem mit dem gesamten Service. |
| `GRPC_STATUS_UNKNOWN` | Ungültige Antwort. |
| `GRPC_STATUS_INTERNAL` | Problem mit Codierung/Dekodierung. |
| `GRPC_STATUS_UNAUTHENTICATED` | Die Authentifizierung ist fehlgeschlagen. |
| `GRPC_STATUS_PERMISSION_DENIED` | Fehler bei der Autorisierung. |
| `GRPC_STATUS_CANCELLED` | Der Anruf wurde abgebrochen, in der Regel vom Anrufer. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>Fehler in ASP.NET Core gRPC erhöhen

Ein ASP.NET Core gRPC-Dienst kann eine `RpcException`Fehlerantwort senden, indem eine ausgelöst wird, die vom Client abgefangen werden kann, als ob sie sich im selben Prozess befänden. Der `RpcException` muss einen Statuscode und eine Beschreibung enthalten und kann optional Metadaten und eine längere Ausnahmemeldung enthalten. Die Metadaten können zum Senden unterstützender `FaultContract` Daten verwendet werden, ähnlich wie Objekte zusätzliche Daten für WCF-Fehler übertragen können.

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

## <a name="catch-errors-in-grpc-clients"></a>Auffangen von Fehlern in gRPC-Clients

Genau wie WCF-Clients Fehler abfangen <xref:System.ServiceModel.FaultException%601> können, `RpcException` kann ein gRPC-Client einen abfangen, um Fehler zu behandeln. Da `RpcException` es sich nicht um einen generischen Typ handelt, können Sie nicht verschiedene Fehlertypen in verschiedenen Blöcken abfangen. Sie können jedoch die *Ausnahmefilterfunktion* von `catch` C verwenden, um separate Blöcke für verschiedene Statuscodes zu deklarieren, wie im folgenden Beispiel gezeigt:

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
> Wenn Sie zusätzliche Metadaten für Fehler bereitstellen, müssen Sie die relevanten Schlüssel und `.proto` Werte in der API-Dokumentation oder in Kommentaren in der Datei dokumentieren.

## <a name="grpc-richer-error-model"></a>gRPC reicheres Fehlermodell

Google hat ein [umfangreicheres Fehlermodell](https://cloud.google.com/apis/design/errors#error_model) entwickelt, das eher WCfs [FaultContract](xref:System.ServiceModel.FaultContractAttribute)ähnelt, aber dieses Modell wird noch nicht in C- unterstützt. Derzeit ist es nur für Go, Java, Python und C++ verfügbar.

>[!div class="step-by-step"]
>[Zurück](metadata.md)
>[Weiter](ws-protocols.md)
