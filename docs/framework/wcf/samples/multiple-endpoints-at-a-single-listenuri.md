---
title: Mehrere Endpunkte unter einem ListenUri
ms.date: 03/30/2017
ms.assetid: 911ffad4-4d47-4430-b7c2-79192ce6bcbd
ms.openlocfilehash: 09696ec8170915f29dae7510f8953565bcc67436
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260187"
---
# <a name="multiple-endpoints-at-a-single-listenuri"></a>Mehrere Endpunkte unter einem ListenUri

In diesem Beispiel wird ein Dienst gezeigt, der mehrere Endpunkte unter einem einzelnen `ListenUri` hostet. Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Wie im Beispiel für [mehrere Endpunkte](multiple-endpoints.md) gezeigt, kann ein Dienst mehrere Endpunkte hosten, die jeweils über unterschiedliche Adressen und möglicherweise auch unterschiedliche Bindungen verfügen. In diesem Beispiel wird gezeigt, dass mehrere Endpunkte auch bei der gleichen Adresse gehostet werden können. Außerdem werden in diesem Beispiel die Unterschiede zwischen den beiden Arten der Adressen eines Dienstendpunkts dargestellt: `EndpointAddress` und `ListenUri`.  
  
 Die `EndpointAddress` ist die logische Adresse eines Diensts. An diese Adresse werden SOAP-Nachrichten adressiert. Der `ListenUri` ist die physische Adresse des Diensts. Er verfügt über die Informationen zu Port und Adresse, an denen der Dienst auf dem aktuellen Computer tatsächlich Nachrichten überwacht. In den meisten Fällen müssen diese Adressen nicht unterschiedlich sein. Wenn ein `ListenUri` nicht explizit angegeben ist, wird er standardmäßig auf den URI der `EndpointAddress` des Endpunkts festgelegt. In einigen Fällen ist es jedoch nützlich, die Adressen zu unterscheiden, z.&#160;B. wenn Sie einen Router konfigurieren, der Nachrichten akzeptiert, die möglicherweise an eine Reihe verschiedener Dienste adressiert sind.  
  
## <a name="service"></a>Dienst  

 Der Dienst in diesem Beispiel besitzt zwei Verträge: `ICalculator` und `IEcho`. Zusätzlich zum üblichen `IMetadataExchange`-Endpunkt gibt es drei Anwendungsendpunkte, wie im folgenden Code gezeigt.  
  
```xml  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.ICalculator"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:Stuff"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
<endpoint address="urn:OtherEcho"  
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IEcho"
        listenUri="http://localhost/servicemodelsamples/service.svc" />  
```  
  
 Alle drei Endpunkte werden unter demselben `ListenUri` gehostet und verwenden dieselbe `binding`. Endpunkte unter demselben `ListenUri` müssen dieselbe Bindung besitzen, da sie gemeinsam einen einzigen Kanalstapel nutzen, der Nachrichten an dieser physischen Adresse des Computers überwacht. Die `address` jedes Endpunkts ist ein URN. Obwohl Adressen in der Regel physische Speicherplätze darstellen, kann die Adresse eigentlich ein beliebiger URI sein, da die Adresse für den Abgleich und die Filterung verwendet wird, wie in diesem Beispiel gezeigt.  
  
 Da alle drei Endpunkte den gleichen nutzen `ListenUri` , wenn eine Nachricht dort eingeht, muss Windows Communication Foundation (WCF) entscheiden, für welchen Endpunkt die Nachricht bestimmt ist. Jeder Endpunkt besitzt einen Nachrichtenfilter, der aus zwei Teilen besteht: dem Adressfilter und dem Vertragsfilter. Der Adressfilter gleicht `To` der SOAP-Nachricht mit der Adresse des Dienstendpunkts ab. So sind beispielsweise nur an `To "Urn:OtherEcho"` adressierte Nachrichten für den dritten Endpunkt dieses Diensts vorgesehen. Der Vertragsfilter gleicht die den Vorgängen eines besonderen Vertrags zugeordneten Aktionen ab. Nachrichten mit der Aktion von `IEcho` `Echo` stimmen beispielsweise mit den Vertragsfiltern des zweiten und dritten Endpunkts dieses Diensts überein, da beide Endpunkte den `IEcho`-Vertrag hosten.  
  
 Deshalb ermöglicht es die Kombination aus Adressfilter und Vertragsfilter, jede am `ListenUri` dieses Diensts eingehende Nachricht zum richtigen Endpunkt weiterzuleiten. Der dritte Endpunkt wird von den anderen beiden unterschieden, da er Nachrichten akzeptiert, die von den anderen Endpunkten an eine andere Adresse gesendet wurden. Der erste und der zweite Endpunkt werden anhand ihrer Verträge (die Aktion der eingehenden Nachricht) voneinander unterschieden.  
  
## <a name="client"></a>Client  

 So wie Endpunkte auf dem Server zwei verschiedene Adressen besitzen, weisen Clientendpunkte auch zwei Adressen auf. Sowohl auf dem Server als auch auf dem Client lautet die logische Adresse `EndpointAddress`. Die physische Adresse wird jedoch auf dem Server `ListenUri` und auf dem Client `Via` genannt.  
  
 Wie auf dem Server sind diese beiden Adressen standardmäßig identisch. Um einen `Via` auf dem Client anzugeben, der sich von der Adresse des Endpunkts unterscheidet, wird `ClientViaBehavior` verwendet:  
  
```csharp  
Uri via = new Uri("http://localhost/ServiceModelSamples/service.svc");  
CalculatorClient calcClient = new CalculatorClient();  
calcClient.ChannelFactory.Endpoint.Behaviors.Add(  
        new ClientViaBehavior(via));  
```  
  
 Wie üblich kommt die Adresse aus der Clientkonfigurationsdatei, die von "Svcutil.exe" generiert wurde. `Via` (entspricht `ListenUri` des Diensts) wird nicht in den Metadaten des Diensts angezeigt, weshalb diese Information dem Client out-of-band mitgeteilt werden muss (genauso wie die Metadatenadresse des Diensts).  
  
 In diesem Beispiel sendet der Client Nachrichten an jeden der drei Endpunkte des Servers, um zu zeigen, dass er mit allen drei Endpunkten kommunizieren (und sie unterscheiden) kann, selbst dann, wenn sie alle denselben `Via` besitzen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
    > [!NOTE]
    > Bei einer computerübergreifenden Konfiguration müssen Sie "localhost" in der Datei "Client.cs" durch den Namen des Dienstcomputers ersetzen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleEndpointsSingleUri`  
