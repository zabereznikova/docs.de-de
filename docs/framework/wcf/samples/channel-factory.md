---
title: Kanalfactory
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: eac315cf88b2ecc7471f194ef6c3be902b3ccbaa
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716048"
---
# <a name="channel-factory"></a>Kanalfactory

In diesem Beispiel wird veranschaulicht, wie eine Clientanwendung einen Kanal mit der <xref:System.ServiceModel.ChannelFactory>-Klasse und nicht mit einem generierten Client erstellen kann. Dieses Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

In diesem Beispiel wird mithilfe der <xref:System.ServiceModel.ChannelFactory%601>-Klasse ein Kanal für einen Dienstendpunkt erstellt. Zum Erstellen eines Kanals zu einem Dienst Endpunkt generieren Sie in der Regel einen Clienttyp mit dem [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) und erstellen eine Instanz des generierten Typs. Sie können einen Kanal auch mithilfe der <xref:System.ServiceModel.ChannelFactory%601>-Klasse erstellen, wie in diesem Beispiel dargestellt. Der mit dem folgenden Beispielcode erstellte Dienst ist [mit dem-Dienst in den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten identisch.

```csharp
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
WSHttpBinding binding = new WSHttpBinding();
ChannelFactory<ICalculator> factory = new
                    ChannelFactory<ICalculator>(binding, address);
ICalculator channel = factory.CreateChannel();
```

> [!IMPORTANT]
> Wenn Sie dieses Beispiel in einem Szenario computerübergreifend ausführen, müssen Sie "localhost" im oben stehenden Code durch den vollqualifizierten Namen des Computers ersetzen, auf dem der Dienst ausgeführt wird. Im Beispiel wird die Endpunktadresse nicht in der Konfiguration festgelegt, daher muss dies im Code erfolgen.

Nach dem Erstellen des Kanals können Dienstvorgänge wie bei einem generierten Client aufgerufen werden.

```csharp
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = channel.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

Zum Schließen des Kanals muss dieser zunächst in eine <xref:System.ServiceModel.IClientChannel>-Schnittstelle umgewandelt werden. Dies ist erforderlich, da der Kanal wie generiert in der Clientanwendung mit der `ICalculator`-Schnittstelle deklariert wird. Diese verfügt über Methoden wie `Add` und `Subtract`, nicht jedoch über `Close`. Die `Close`-Methode stammt aus der <xref:System.ServiceModel.ICommunicationObject>-Schnittstelle.

```csharp
// Close the channel.
 ((IClientChannel)client).Close();
```

Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um die Clientanwendung zu schließen.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen. Beachten Sie, dass das Veröffentlichen von Metadaten in diesem Beispiel nicht aktiviert wird. Sie müssen zuerst das Veröffentlichen von Metadaten aktivieren, damit der Clienttyp in diesem Beispiel erneut generiert wird.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-cross-machine"></a>So führen Sie das Beispiel computerübergreifend aus

1. Ersetzen Sie "localhost" im folgenden Code durch den vollqualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird.

    ```csharp
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
    ```

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`
