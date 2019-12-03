---
title: Benutzerdefinierter Nachrichtenfilter
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 79edba14eff5403591cf43592415d923dbd321be
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716831"
---
# <a name="custom-message-filter"></a>Benutzerdefinierter Nachrichtenfilter
In diesem Beispiel wird veranschaulicht, wie die Nachrichtenfilter ersetzt werden, die Windows Communication Foundation (WCF) verwendet, um Nachrichten an Endpunkte zu senden.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Wenn die erste Nachricht auf einem Kanal beim Server eintrifft, muss der Server bestimmen, welcher der mit diesem URI verknüpften Endpunkte (sofern zutreffend) die Nachricht erhalten soll. Dieser Prozess wird von den an den <xref:System.ServiceModel.Dispatcher.MessageFilter> angefügten <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Objekten kontrolliert.  
  
 Jeder Endpunkt eines Diensts hat einen einzelnen <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>. Der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> besitzt sowohl einen <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> als auch einen <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>. Die Verbindung dieser beiden Filter ist der für diesen Endpunkt verwendete Nachrichtenfilter.  
  
 Standardmäßig stimmt der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> für einen Endpunkt mit jeder Nachricht überein, die an eine Adresse gesendet wird, die wiederum mit der <xref:System.ServiceModel.EndpointAddress> des Dienstendpunkts übereinstimmt. Standardmäßig überprüft der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> für einen Endpunkt die Aktion der eingehenden Nachricht und gleicht jede Nachricht mit einer Aktion ab, die einer der Aktionen der Vorgänge des dienstend Punkt Vertrags entspricht (nur `IsInitiating`=`true` Aktionen berücksichtigt werden). Demzufolge stimmt der Filter für einen Endpunkt standardmäßig nur überein, wenn sowohl der To-Header der Nachricht die <xref:System.ServiceModel.EndpointAddress> des Endpunkts ist als auch die Aktion der Nachricht mit einer der Aktionen der Endpunktvorgänge übereinstimmt.  
  
 Diese Filter können mit einer Verhaltensweise geändert werden. Im folgenden Beispiel erstellt der Dienst ein <xref:System.ServiceModel.Description.IEndpointBehavior>, das den <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> und den <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> auf dem <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> ersetzt:  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 Es werden zwei Adressfilter definiert:  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 Das `FilteringEndpointBehavior` wird konfigurierbar gemacht und ermöglicht zwei verschiedene Varianten.  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 Variante&#160;1 gleicht nur Adressen ab, die ein "e" (aber eine beliebige Aktion) enthalten, wohingegen Variante&#160;2 nur die Adressen ohne "e" abgleicht:  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 Der Dienst registriert das neue Verhalten in der Konfigurationsdatei:  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>      
```  
  
 Anschließend erstellt der Dienst `endpointBehavior`-Konfigurationen für jede Variante:  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 Schließlich verweist der Endpunkt des Diensts auf eine der `behaviorConfigurations`:  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""   
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"   
        behaviorConfiguration="endpoint2" />  
```  
  
 Die Implementierung der Clientanwendung ist einfach. Sie erstellt zwei Kanäle zum URI des Diensts (indem der Wert als der zweite (`via`)-Parameter an <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> übergeben wird) und sendet eine einzelne Nachricht auf jedem Kanal, verwendet aber jeweils verschiedene Endpunktadressen. Infolgedessen besitzen die vom Client ausgehenden Nachrichten unterschiedliche To-Ziele, und der Server antwortet entsprechend, wie von der Ausgabe des Clients veranschaulicht:  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 Durch einen Wechsel der Variante in der Konfigurationsdatei des Servers wird der Filter getauscht, und der Client sieht das andere Verhalten (die Nachricht an `urn:e` ist erfolgreich, die Nachricht an `urn:a` jedoch nicht).  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""   
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"   
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.  
  
2. Um das Beispiel in einer Konfiguration mit einem einzelnen Computer auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
3. Um das Beispiel in einer Computer übergreifenden Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) , und ändern Sie die folgende Zeile in Client.cs.  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     Ersetzen Sie "localhost" mit dem Namen des Servers.  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
