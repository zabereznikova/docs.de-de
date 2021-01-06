---
title: Vergleichen von WCF mit GrpC-GrpC für WCF-Entwickler
description: Ein Vergleich der WCF-und GrpC-Frameworks zum entwickeln verteilter Anwendungen.
ms.date: 12/15/2020
ms.openlocfilehash: 7dd41c3d6f248bb1ef5eacb323b1443c7bc575a7
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938493"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="1618e-103">Vergleichen von WCF mit GrpC</span><span class="sxs-lookup"><span data-stu-id="1618e-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="1618e-104">Im vorherigen Kapitel haben Sie einen guten Einblick in protobuf und die Art und Weise erläutert, wie GrpC Nachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1618e-104">The previous chapter gave you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="1618e-105">Bevor Sie eine ausführliche Konvertierung von Windows Communication Foundation (WCF) zu GrpC durchführen, ist es wichtig, dass die in WCF verfügbaren Features in GrpC behandelt werden und welche Problem Umgehungen Sie verwenden können, wenn keine GrpC-Entsprechung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1618e-105">Before you work through a detailed conversion from Windows Communication Foundation (WCF) to gRPC, it's important know how the features available in WCF are handled in gRPC and what workarounds you can use when there's no gRPC equivalent.</span></span> <span data-ttu-id="1618e-106">In diesem Kapitel werden insbesondere die folgenden Themen behandelt:</span><span class="sxs-lookup"><span data-stu-id="1618e-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="1618e-107">Vorgänge und Methoden</span><span class="sxs-lookup"><span data-stu-id="1618e-107">Operations and methods</span></span>
- <span data-ttu-id="1618e-108">Bindungen und Transporte</span><span class="sxs-lookup"><span data-stu-id="1618e-108">Bindings and transports</span></span>
- <span data-ttu-id="1618e-109">RPC-Typen</span><span class="sxs-lookup"><span data-stu-id="1618e-109">RPC types</span></span>
- <span data-ttu-id="1618e-110">Metadaten</span><span class="sxs-lookup"><span data-stu-id="1618e-110">Metadata</span></span>
- <span data-ttu-id="1618e-111">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="1618e-111">Error handling</span></span>
- <span data-ttu-id="1618e-112">WS- \* Protokolle</span><span class="sxs-lookup"><span data-stu-id="1618e-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="1618e-113">GrpC-Beispiel</span><span class="sxs-lookup"><span data-stu-id="1618e-113">gRPC example</span></span>

<span data-ttu-id="1618e-114">Wenn Sie ein neues ASP.net Core 5,0 GrpC-Projekt aus Visual Studio 2019 oder der Befehlszeile erstellen, wird die GrpC-Entsprechung von "Hallo Welt" für Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="1618e-114">When you create a new ASP.NET Core 5.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="1618e-115">Er besteht aus einer `greeter.proto` Datei, die den Dienst und seine Nachrichten definiert, und einer `GreeterService.cs` Datei mit einer Implementierung des Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="1618e-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message that contains the user's name.
message HelloRequest {
  string name = 1;
}

// The response message that contains the greetings.
message HelloReply {
  string message = 1;
}
```

```csharp
using System.Threading.Tasks;
using Grpc.Core;
using Microsoft.Extensions.Logging;

namespace HelloGrpc
{
    public class GreeterService : Greeter.GreeterBase
    {
        private readonly ILogger<GreeterService> _logger;
        public GreeterService(ILogger<GreeterService> logger)
        {
            _logger = logger;
        }

        public override Task<HelloReply> SayHello(HelloRequest request, ServerCallContext context)
        {
            return Task.FromResult(new HelloReply
            {
                Message = "Hello " + request.Name
            });
        }
    }
}
```

<span data-ttu-id="1618e-116">Dieses Kapitel bezieht sich auf diesen Beispielcode, wenn verschiedene Konzepte und Features von GrpC erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="1618e-116">This chapter will refer to this example code when explaining different concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1618e-117">[Zurück](protobuf-maps.md)
>[Weiter](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="1618e-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
