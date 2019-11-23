---
title: Vergleichen von WCF mit GrpC-GrpC für WCF-Entwickler
description: Ein Vergleich der WCF-und GrpC-Frameworks zum entwickeln verteilter Anwendungen.
ms.date: 09/02/2019
ms.openlocfilehash: 312492dcce4bdef61feff0bf924c6df287b9c676
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966952"
---
# <a name="comparing-wcf-to-grpc"></a>Vergleichen von WCF mit GrpC

Im vorherigen Kapitel sollte ein guter Einblick in protobuf und die Art und Weise erläutert werden, wie GrpC Nachrichten verarbeitet. Vor der detaillierten Konvertierung von WCF in GrpC ist es wichtig, zu überprüfen, wie die derzeit in WCF verfügbaren Features in GrpC behandelt werden und welche Problem Umgehungen Sie verwenden können, wenn keine GrpC-Entsprechung vorhanden ist. In diesem Kapitel werden insbesondere die folgenden Themen behandelt:

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

Dieses Kapitel bezieht sich auf diesen Beispielcode, wenn verschiedene Konzepte und Features von GrpC erläutert werden.

>[!div class="step-by-step"]
>[Zurück](protobuf-maps.md)
>[Weiter](wcf-endpoints-grpc-methods.md)
