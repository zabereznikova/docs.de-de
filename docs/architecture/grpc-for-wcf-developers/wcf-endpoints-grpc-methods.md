---
title: 'WCF-Endpunkte und GrpC-Methoden: GrpC für WCF-Entwickler'
description: Vergleich von WCF-Endpunkten, die mit den Attributen ServiceContract und OperationContract deklariert wurden, und den in protobuf deklarierten GrpC-Methoden
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1cb7fedf1fbb632438134375306801f356d7b921
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841300"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>WCF-Endpunkte und GrpC-Methoden

Wenn Sie in WCF den Anwendungscode schreiben, verwenden Sie eine der folgenden Methoden:

- Sie schreiben den Anwendungscode in einer Klasse und ergänzen Methoden mit dem [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut.
- Sie deklarieren eine Schnittstelle für den Dienst und fügen [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribute zur Schnittstelle hinzu.

Beispielsweise könnte die WCF-Entsprechung des `greet.proto` Greeter-Dienstanbieter wie folgt geschrieben werden:

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

Kapitel 3 zeigte, dass protobuf-Nachrichten Definitionen verwendet werden, um Daten Klassen zu generieren. Dienst-und Methoden Deklarationen werden verwendet, um Basisklassen zu generieren, von denen Sie erben, um den Dienst zu implementieren. Sie deklarieren nur die Methoden, die in der `.proto`-Datei implementiert werden sollen, und der Compiler generiert eine Basisklasse mit virtuellen Methoden, die Sie überschreiben müssen.

## <a name="operationcontract-properties"></a>OperationContract-Eigenschaften

Das [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut verfügt über Eigenschaften zum Steuern oder verfeinern der Funktionsweise. GrpC-Methoden bieten diese Art von Kontrolle nicht. In der folgenden Tabelle werden diese `OperationContract` Eigenschaften festgelegt, und es wird erläutert, wie die von Ihnen angegebene Funktionalität in GrpC behandelt wird:

| `OperationContract` -Eigenschaft | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | Der URI, der den Vorgang identifiziert. GrpC verwendet den Namen der `package`, `service` und `rpc` aus der `.proto` Datei. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Alle GrpC-Dienst Methoden geben `Task` Objekte zurück. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | Siehe den Hinweis unten. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | Unidirektionale GrpC-Methoden geben `Empty` Ergebnisse zurück oder verwenden Client-Streaming. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | Siehe den Hinweis unten. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | SOAP-bezogen, keine Bedeutung in GrpC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | Keine Nachrichten Verschlüsselung; die Netzwerk Verschlüsselung wird auf Transport Ebene (TLS über http/2) verarbeitet. |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | SOAP-bezogen, keine Bedeutung in GrpC. |

Mit der `IsInitiating`-Eigenschaft können Sie angeben, dass eine Methode in einem [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) nicht als erste Methode aufgerufen werden kann, die als Teil einer Sitzung aufgerufen wird. Die `IsTerminating`-Eigenschaft bewirkt, dass der Server die Sitzung schließt, nachdem ein Vorgang aufgerufen wurde (oder der Client, wenn er auf einem Rückruf Client verwendet wird). In GrpC werden Streams von einzelnen Methoden erstellt und explizit geschlossen. Siehe [GrpC Streaming](rpc-types.md#grpc-streaming).

Weitere Informationen zur Sicherheit und Verschlüsselung von GrpC finden Sie in [Kapitel 6](security.md).

>[!div class="step-by-step"]
>[Zurück](wcf-services-to-grpc-comparison.md)
>[Weiter](wcf-bindings.md)
