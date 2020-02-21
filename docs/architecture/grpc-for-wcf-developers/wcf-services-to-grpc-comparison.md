---
title: Vergleichen von WCF mit GrpC-GrpC für WCF-Entwickler
description: Ein Vergleich der WCF-und GrpC-Frameworks zum entwickeln verteilter Anwendungen.
ms.date: 09/02/2019
ms.openlocfilehash: 4f54db76c9512b770b4dd993496d95437dd89753
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503333"
---
# <a name="comparing-wcf-to-grpc"></a>Vergleichen von WCF mit GrpC

Im vorherigen Kapitel haben Sie einen guten Einblick in protobuf und die Art und Weise erläutert, wie GrpC Nachrichten verarbeitet. Bevor Sie eine ausführliche Konvertierung von Windows Communication Foundation (WCF) zu GrpC durchführen, ist es wichtig, dass die in WCF verfügbaren Features in GrpC behandelt werden und welche Problem Umgehungen Sie verwenden können, wenn keine GrpC-Entsprechung vorhanden ist. In diesem Kapitel werden insbesondere die folgenden Themen behandelt:

- Vorgänge und Methoden
- Bindungen und Transporte
- RPC-Typen
- Metadaten
- Fehlerbehandlung
- WS-\* Protokolle

## <a name="grpc-example"></a>GrpC-Beispiel

Wenn Sie ein neues ASP.net Core 3,0 GrpC-Projekt aus Visual Studio 2019 oder der Befehlszeile erstellen, wird die GrpC-Entsprechung von "Hallo Welt" für Sie generiert. Er besteht aus einer `greeter.proto`-Datei, die den Dienst und seine Nachrichten definiert, und einer `GreeterService.cs` Datei mit einer Implementierung des Dienstanbieter.

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

Dieses Kapitel bezieht sich auf diesen Beispielcode, wenn verschiedene Konzepte und Features von GrpC erläutert werden.

>[!div class="step-by-step"]
>[Zurück](protobuf-maps.md)
>[Weiter](wcf-endpoints-grpc-methods.md)
