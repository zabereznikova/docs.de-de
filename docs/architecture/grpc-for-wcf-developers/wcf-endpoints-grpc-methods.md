---
title: 'WCF-Endpunkte und GrpC-Methoden: GrpC für WCF-Entwickler'
description: Vergleich von WCF-Endpunkten, die mit den Attributen ServiceContract und OperationContract deklariert wurden, und den in protobuf deklarierten GrpC-Methoden
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503429"
---
# <a name="wcf-endpoints-and-grpc-methods"></a>WCF-Endpunkte und GrpC-Methoden

Wenn Sie in Windows Communication Foundation (WCF) den Anwendungscode schreiben, verwenden Sie eine der folgenden Methoden:

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

Das [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut verfügt über Eigenschaften zum Steuern oder verfeinern der Funktionsweise. GrpC-Methoden bieten diese Art von Kontrolle nicht. In der folgenden Tabelle sind die `OperationContract` Eigenschaften aufgeführt, und es wird beschrieben, wie die von Ihnen angegebenen Funktionen in GrpC behandelt werden:

| `OperationContract`-Eigenschaft | gRPC                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | Ein URI identifiziert den Vorgang. GrpC verwendet den Namen `package`, `service`und `rpc` aus der `.proto` Datei. |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | Alle GrpC-Dienst Methoden geben `Task` Objekte zurück. |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | Weitere Informationen finden Sie im Absatz nach dieser Tabelle. |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | Unidirektionale GrpC-Methoden geben `Empty` Ergebnisse zurück oder verwenden Client-Streaming. |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | Weitere Informationen finden Sie im Absatz nach dieser Tabelle. |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | Diese Eigenschaft ist SOAP-bezogen und hat keine Bedeutung in GrpC. |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | Es gibt keine Nachrichten Verschlüsselung. Die Netzwerk Verschlüsselung wird auf Transport Ebene (TLS über http/2) gehandhabt. |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | Diese Eigenschaft ist SOAP-bezogen und hat keine Bedeutung in GrpC. |

Mit der `IsInitiating`-Eigenschaft können Sie angeben, dass eine Methode in [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) nicht als erste Methode aufgerufen werden kann, die als Teil einer Sitzung aufgerufen wird. Die `IsTerminating`-Eigenschaft bewirkt, dass der Server die Sitzung schließt, nachdem ein Vorgang aufgerufen wurde (oder der Client, wenn die-Eigenschaft auf einem Rückruf Client verwendet wird). In GrpC werden Streams von einzelnen Methoden erstellt und explizit geschlossen. Siehe [GrpC Streaming](rpc-types.md#grpc-streaming).

Weitere Informationen zur Sicherheit und Verschlüsselung von GrpC finden Sie in [Kapitel 6](security.md).

>[!div class="step-by-step"]
>[Zurück](wcf-services-to-grpc-comparison.md)
>[Weiter](wcf-bindings.md)
