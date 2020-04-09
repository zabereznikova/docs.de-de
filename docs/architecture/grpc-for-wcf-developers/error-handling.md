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
# <a name="error-handling"></a><span data-ttu-id="5fa7d-104">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="5fa7d-104">Error handling</span></span>

<span data-ttu-id="5fa7d-105">Windows Communication Foundation (WCF) verwendet <xref:System.ServiceModel.FaultException%601> und [FaultContract](xref:System.ServiceModel.FaultContractAttribute) verwendet, um detaillierte Fehlerinformationen bereitzustellen, einschließlich der Unterstützung des SOAP Fault-Standards.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="5fa7d-106">Leider fehlt der aktuellen Version von gRPC die mit WCF gefundene Raffinesse und es gibt nur eine begrenzte integrierte Fehlerbehandlung basierend auf einfachen Statuscodes und Metadaten.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="5fa7d-107">Die folgende Tabelle enthält eine Kurzanleitung zu den am häufigsten verwendeten Statuscodes:</span><span class="sxs-lookup"><span data-stu-id="5fa7d-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="5fa7d-108">Statuscode</span><span class="sxs-lookup"><span data-stu-id="5fa7d-108">Status code</span></span> | <span data-ttu-id="5fa7d-109">Problem</span><span class="sxs-lookup"><span data-stu-id="5fa7d-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="5fa7d-110">Die Methode wurde nicht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="5fa7d-111">Problem mit dem gesamten Service.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="5fa7d-112">Ungültige Antwort.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="5fa7d-113">Problem mit Codierung/Dekodierung.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="5fa7d-114">Die Authentifizierung ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="5fa7d-115">Fehler bei der Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="5fa7d-116">Der Anruf wurde abgebrochen, in der Regel vom Anrufer.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="5fa7d-117">Fehler in ASP.NET Core gRPC erhöhen</span><span class="sxs-lookup"><span data-stu-id="5fa7d-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="5fa7d-118">Ein ASP.NET Core gRPC-Dienst kann eine `RpcException`Fehlerantwort senden, indem eine ausgelöst wird, die vom Client abgefangen werden kann, als ob sie sich im selben Prozess befänden.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="5fa7d-119">Der `RpcException` muss einen Statuscode und eine Beschreibung enthalten und kann optional Metadaten und eine längere Ausnahmemeldung enthalten.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="5fa7d-120">Die Metadaten können zum Senden unterstützender `FaultContract` Daten verwendet werden, ähnlich wie Objekte zusätzliche Daten für WCF-Fehler übertragen können.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="5fa7d-121">Auffangen von Fehlern in gRPC-Clients</span><span class="sxs-lookup"><span data-stu-id="5fa7d-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="5fa7d-122">Genau wie WCF-Clients Fehler abfangen <xref:System.ServiceModel.FaultException%601> können, `RpcException` kann ein gRPC-Client einen abfangen, um Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="5fa7d-123">Da `RpcException` es sich nicht um einen generischen Typ handelt, können Sie nicht verschiedene Fehlertypen in verschiedenen Blöcken abfangen.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="5fa7d-124">Sie können jedoch die *Ausnahmefilterfunktion* von `catch` C verwenden, um separate Blöcke für verschiedene Statuscodes zu deklarieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5fa7d-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="5fa7d-125">Wenn Sie zusätzliche Metadaten für Fehler bereitstellen, müssen Sie die relevanten Schlüssel und `.proto` Werte in der API-Dokumentation oder in Kommentaren in der Datei dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="5fa7d-126">gRPC reicheres Fehlermodell</span><span class="sxs-lookup"><span data-stu-id="5fa7d-126">gRPC richer error model</span></span>

<span data-ttu-id="5fa7d-127">Google hat ein [umfangreicheres Fehlermodell](https://cloud.google.com/apis/design/errors#error_model) entwickelt, das eher WCfs [FaultContract](xref:System.ServiceModel.FaultContractAttribute)ähnelt, aber dieses Modell wird noch nicht in C- unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="5fa7d-128">Derzeit ist es nur für Go, Java, Python und C++ verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5fa7d-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5fa7d-129">[Zurück](metadata.md)
>[Weiter](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="5fa7d-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
