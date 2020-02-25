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
# <a name="error-handling"></a><span data-ttu-id="ec8f9-104">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="ec8f9-104">Error handling</span></span>

<span data-ttu-id="ec8f9-105">Windows Communication Foundation (WCF) verwendet <xref:System.ServiceModel.FaultException%601> und " [fehlercontract](xref:System.ServiceModel.FaultContractAttribute) ", um ausführliche Fehlerinformationen bereitzustellen, einschließlich der Unterstützung des SOAP-Fehler Standards.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="ec8f9-106">Leider fehlt in der aktuellen Version von GrpC die Komplexität, die mit WCF gefunden wurde, und Sie verfügt nur über eine begrenzte Integrierte Fehlerbehandlung, die auf einfachen Statuscodes und Metadaten basiert.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="ec8f9-107">In der folgenden Tabelle finden Sie eine kurze Anleitung zu den am häufigsten verwendeten Statuscodes:</span><span class="sxs-lookup"><span data-stu-id="ec8f9-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="ec8f9-108">Statuscode</span><span class="sxs-lookup"><span data-stu-id="ec8f9-108">Status code</span></span> | <span data-ttu-id="ec8f9-109">Problem</span><span class="sxs-lookup"><span data-stu-id="ec8f9-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="ec8f9-110">Die Methode wurde nicht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-110">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="ec8f9-111">Problem mit dem gesamten Dienst.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="ec8f9-112">Ungültige Antwort.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="ec8f9-113">Problem beim Codieren/Decodieren.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="ec8f9-114">Die Authentifizierung ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="ec8f9-115">Fehler bei der Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="ec8f9-116">Der Aufruf wurde abgebrochen, normalerweise durch den Aufrufer.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="ec8f9-117">Fehler in ASP.net Core GrpC</span><span class="sxs-lookup"><span data-stu-id="ec8f9-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="ec8f9-118">Ein ASP.net Core GrpC-Dienst kann eine Fehler Antwort senden, indem er eine `RpcException`auslöst, die vom Client abgefangen werden kann, als ob er sich im selben Prozess befindet.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="ec8f9-119">Der `RpcException` muss einen Statuscode und eine Beschreibung enthalten und optional Metadaten und eine längere Ausnahme Meldung enthalten.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="ec8f9-120">Die Metadaten können verwendet werden, um unterstützende Daten zu senden, ähnlich wie `FaultContract` Objekten zusätzliche Daten für WCF-Fehler enthalten können.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="ec8f9-121">Catch-Fehler in GrpC-Clients</span><span class="sxs-lookup"><span data-stu-id="ec8f9-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="ec8f9-122">Ebenso wie WCF-Clients <xref:System.ServiceModel.FaultException%601> Fehler erfassen können, kann ein GrpC-Client eine `RpcException` abfangen, um Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="ec8f9-123">Da `RpcException` kein generischer Typ ist, können Sie verschiedene Fehlertypen in unterschiedlichen Blöcken nicht erfassen.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="ec8f9-124">Sie können jedoch die C# *Ausnahme Filter* Funktion verwenden, um separate `catch` Blöcke für verschiedene Statuscodes zu deklarieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec8f9-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="ec8f9-125">Wenn Sie zusätzliche Metadaten für Fehler bereitstellen, stellen Sie sicher, dass Sie die relevanten Schlüssel und Werte in der API-Dokumentation oder in Kommentaren in der `.proto`-Datei dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="ec8f9-126">umfangreicheres GrpC-Fehlermodell</span><span class="sxs-lookup"><span data-stu-id="ec8f9-126">gRPC richer error model</span></span>

<span data-ttu-id="ec8f9-127">Google hat ein Umfang [reicheres Fehlermodell](https://cloud.google.com/apis/design/errors#error_model) entwickelt, das eher wie der WCF-Fehler [Vertrag](xref:System.ServiceModel.FaultContractAttribute), aber dieses Modell C# wird noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="ec8f9-128">Derzeit ist Sie nur für Go, Java, Python und C++verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ec8f9-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ec8f9-129">[Zurück](metadata.md)
>[Weiter](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="ec8f9-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
