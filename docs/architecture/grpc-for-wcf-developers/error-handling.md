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
# <a name="error-handling"></a><span data-ttu-id="2882e-103">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="2882e-103">Error handling</span></span>

<span data-ttu-id="2882e-104">WCF verwendet `FaultException<T>` und `FaultContract`, um detaillierte Fehlerinformationen bereitzustellen, einschließlich der Unterstützung des SOAP-Fehler Standards.</span><span class="sxs-lookup"><span data-stu-id="2882e-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="2882e-105">Leider fehlt in der aktuellen Version von GrpC die Komplexität, die mit WCF gefunden wurde, und Sie verfügt nur über eine begrenzte Integrierte Fehlerbehandlung, die auf einfachen Statuscodes und Metadaten basiert.</span><span class="sxs-lookup"><span data-stu-id="2882e-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="2882e-106">In der folgenden Tabelle finden Sie eine kurze Anleitung zu den am häufigsten verwendeten Statuscodes:</span><span class="sxs-lookup"><span data-stu-id="2882e-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="2882e-107">Statuscode</span><span class="sxs-lookup"><span data-stu-id="2882e-107">Status Code</span></span> | <span data-ttu-id="2882e-108">Problem</span><span class="sxs-lookup"><span data-stu-id="2882e-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="2882e-109">Die Methode wurde nicht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="2882e-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="2882e-110">Problem mit dem gesamten Dienst.</span><span class="sxs-lookup"><span data-stu-id="2882e-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="2882e-111">Ungültige Antwort.</span><span class="sxs-lookup"><span data-stu-id="2882e-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="2882e-112">Problem beim Codieren/Decodieren.</span><span class="sxs-lookup"><span data-stu-id="2882e-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="2882e-113">Fehler bei der Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2882e-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="2882e-114">Autorisierungs Fehler.</span><span class="sxs-lookup"><span data-stu-id="2882e-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="2882e-115">Der Aufruf wurde abgebrochen, normalerweise durch den Aufrufer.</span><span class="sxs-lookup"><span data-stu-id="2882e-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="2882e-116">Fehler beim Auftreten von Fehlern in ASP.net Core GrpC</span><span class="sxs-lookup"><span data-stu-id="2882e-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="2882e-117">Ein ASP.net Core GrpC-Dienst kann eine Fehler Antwort senden, indem er eine `RpcException`auslöst, die vom Client abgefangen werden kann, als ob er sich im selben Prozess befindet.</span><span class="sxs-lookup"><span data-stu-id="2882e-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="2882e-118">Der `RpcException` muss einen Statuscode und eine Beschreibung enthalten und optional Metadaten und eine längere Ausnahme Meldung enthalten.</span><span class="sxs-lookup"><span data-stu-id="2882e-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="2882e-119">Die Metadaten können verwendet werden, um unterstützende Daten zu senden, ähnlich wie `FaultContract` Objekten zusätzliche Daten für WCF-Fehler enthalten könnten.</span><span class="sxs-lookup"><span data-stu-id="2882e-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

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

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="2882e-120">Abfangen von Fehlern in GrpC-Clients</span><span class="sxs-lookup"><span data-stu-id="2882e-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="2882e-121">Ebenso wie WCF-Clients <xref:System.ServiceModel.FaultException%601> Fehler erfassen können, kann ein GrpC-Client eine `RpcException` abfangen, um Fehler zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="2882e-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="2882e-122">Da `RpcException` kein generischer Typ ist, können Sie verschiedene Fehlertypen nicht in unterschiedlichen Blöcken erfassen, aber C#Sie können die *Ausnahme Filter* Funktion verwenden, um separate `catch` Blöcke für verschiedene Statuscodes zu deklarieren, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2882e-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="2882e-123">Wenn Sie zusätzliche Metadaten für Fehler bereitstellen, stellen Sie sicher, dass Sie die relevanten Schlüssel und Werte in der API-Dokumentation oder in Kommentaren in der `.proto`-Datei dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="2882e-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="2882e-124">umfangreicheres GrpC-Fehlermodell</span><span class="sxs-lookup"><span data-stu-id="2882e-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="2882e-125">In C# der Vorschau hat Google ein Umfang [reicheres Fehlermodell](https://cloud.google.com/apis/design/errors#error_model) [entwickelt, das besser wie der von](xref:System.ServiceModel.FaultContractAttribute)WCF ist, aber noch nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2882e-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="2882e-126">Derzeit ist Sie nur für Go, Java, Python und C++verfügbar, aber die Unterstützung C# für wird im nächsten Jahr erwartet.</span><span class="sxs-lookup"><span data-stu-id="2882e-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2882e-127">[Zurück](metadata.md)
>[Weiter](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="2882e-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
