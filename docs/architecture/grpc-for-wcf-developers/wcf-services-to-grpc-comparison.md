---
title: Vergleichen von WCF mit GrpC-GrpC für WCF-Entwickler
description: Ein Vergleich der WCF-und GrpC-Frameworks zum entwickeln verteilter Anwendungen.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5ab1380d4ded52abff08c35c430adf2f3ed7c58b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841294"
---
# <a name="comparing-wcf-to-grpc"></a><span data-ttu-id="c09e7-103">Vergleichen von WCF mit GrpC</span><span class="sxs-lookup"><span data-stu-id="c09e7-103">Comparing WCF to gRPC</span></span>

<span data-ttu-id="c09e7-104">Im vorherigen Kapitel sollte ein guter Einblick in protobuf und die Art und Weise erläutert werden, wie GrpC Nachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c09e7-104">The previous chapter should have given you a good look at Protobuf and how gRPC handles messages.</span></span> <span data-ttu-id="c09e7-105">Vor der detaillierten Konvertierung von WCF in GrpC ist es wichtig, zu überprüfen, wie die derzeit in WCF verfügbaren Features in GrpC behandelt werden und welche Problem Umgehungen Sie verwenden können, wenn keine GrpC-Entsprechung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c09e7-105">Before working through a detailed conversion from WCF to gRPC, it's important to look at how the range of features currently available in WCF are handled in gRPC and what workarounds you can use when there doesn't appear to be a gRPC equivalent.</span></span> <span data-ttu-id="c09e7-106">In diesem Kapitel werden insbesondere die folgenden Themen behandelt:</span><span class="sxs-lookup"><span data-stu-id="c09e7-106">In particular, this chapter will cover the following subjects:</span></span>

- <span data-ttu-id="c09e7-107">Vorgänge und Methoden</span><span class="sxs-lookup"><span data-stu-id="c09e7-107">Operations and methods</span></span>
- <span data-ttu-id="c09e7-108">Bindungen und Transporte</span><span class="sxs-lookup"><span data-stu-id="c09e7-108">Bindings and transports</span></span>
- <span data-ttu-id="c09e7-109">RPC-Typen</span><span class="sxs-lookup"><span data-stu-id="c09e7-109">RPC types</span></span>
- <span data-ttu-id="c09e7-110">Metadaten</span><span class="sxs-lookup"><span data-stu-id="c09e7-110">Metadata</span></span>
- <span data-ttu-id="c09e7-111">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="c09e7-111">Error handling</span></span>
- <span data-ttu-id="c09e7-112">WS-\* Protokolle</span><span class="sxs-lookup"><span data-stu-id="c09e7-112">WS-\* protocols</span></span>

## <a name="grpc-example"></a><span data-ttu-id="c09e7-113">GrpC-Beispiel</span><span class="sxs-lookup"><span data-stu-id="c09e7-113">gRPC example</span></span>

<span data-ttu-id="c09e7-114">Wenn Sie ein neues ASP.net Core 3,0 GrpC-Projekt aus Visual Studio 2019 oder der Befehlszeile erstellen, wird die GrpC-Entsprechung von "Hallo Welt" für Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="c09e7-114">When you create a new ASP.NET Core 3.0 gRPC project from Visual Studio 2019 or the command line, the gRPC equivalent of "Hello World" is generated for you.</span></span> <span data-ttu-id="c09e7-115">Er besteht aus einer `greeter.proto`-Datei, die den Dienst und seine Nachrichten definiert, und einer `GreeterService.cs` Datei mit einer Implementierung des Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="c09e7-115">It consists of a `greeter.proto` file that defines the service and its messages, and a `GreeterService.cs` file with an implementation of the service.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "HelloGrpc";

package Greet;

// The greeting service definition.
service Greeter {
  // Sends a greeting
  rpc SayHello (HelloRequest) returns (HelloReply);
}

// The request message containing the user's name.
message HelloRequest {
  string name = 1;
}

// The response message containing the greetings.
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

<span data-ttu-id="c09e7-116">Dieses Kapitel bezieht sich auf diesen Beispielcode, wenn verschiedene Konzepte und Features von GrpC erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="c09e7-116">This chapter will refer to this example code when explaining various concepts and features of gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c09e7-117">[Zurück](protobuf-maps.md)
>[Weiter](wcf-endpoints-grpc-methods.md)</span><span class="sxs-lookup"><span data-stu-id="c09e7-117">[Previous](protobuf-maps.md)
[Next](wcf-endpoints-grpc-methods.md)</span></span>
