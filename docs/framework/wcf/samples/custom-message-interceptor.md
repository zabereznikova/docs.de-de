---
title: Benutzerdefinierter Nachrichteninterceptor
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 53005212bc834d73ab5cbb4545d1477112f29c75
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716813"
---
# <a name="custom-message-interceptor"></a>Benutzerdefinierter Nachrichteninterceptor
In diesem Beispiel wird die Verwendung des Kanalerweiterbarkeitsmodells veranschaulicht. Es zeigt insbesondere, wie ein benutzerdefiniertes Bindungselement implementiert wird, das Kanalfactorys und Kanallistener erstellt, um sämtliche ein- und ausgehenden Nachrichten an einer bestimmten Stelle im Laufzeitstapel abzufangen. Im Beispiel sind auch ein Client und ein Server, die die Verwendung dieser benutzerdefinierten Factorys veranschaulichen, enthalten.  
  
 In diesem Beispiel sind sowohl der Client als auch der Dienst Konsolenprogramme (.exe). Der Client und der Dienst verwenden beide eine allgemeine Bibliothek (.dll), die das benutzerdefinierte Bindungselement und zugewiesene Laufzeitobjekte enthält.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 Im Beispiel wird die empfohlene Vorgehensweise zum Erstellen eines benutzerdefinierten geschichteten Kanals in Windows Communication Foundation (WCF) mithilfe des Channel-Frameworks und der folgenden bewährten WCF-Methoden beschrieben. Mit folgenden Schritten wird ein benutzerdefinierter geschichteter Kanal erstellt:  
  
1. Legen Sie fest, welche Kanalform die Kanalfactory und der Kanallistener unterstützen sollen.  
  
2. Erstellen Sie eine Kanalfactory und einen Kanallistener, die Ihre Kanalformen unterstützen.  
  
3. Fügen Sie ein Bindungselement hinzu, das den benutzerdefinierten geschichteten Kanal einem Kanalstapel hinzufügt.  
  
4. Fügen Sie einen Bindungselementerweiterungs-Abschnitt hinzu, um das neue Bindungselement für das Konfigurationssystem verfügbar zu machen.  
  
## <a name="channel-shapes"></a>Kanalformen  
 Der erste Schritt beim Schreiben eines benutzerdefinierten geschichteten Kanals besteht darin zu entscheiden, welche Formen für den Kanal erforderlich sind. Bei unserem Nachrichteninspektor wird jede Form unterstützt, die die Schicht unterhalb unterstützt (wenn die Schicht unterhalb beispielsweise <xref:System.ServiceModel.Channels.IOutputChannel> und <xref:System.ServiceModel.Channels.IDuplexSessionChannel> erstellen kann, werden ebenfalls <xref:System.ServiceModel.Channels.IOutputChannel> und <xref:System.ServiceModel.Channels.IDuplexSessionChannel> verfügbar gemacht).  
  
## <a name="channel-factory-and-listener-factory"></a>Kanalfactory und Listenerfactory  
 Der nächste Schritt beim Schreiben eines benutzerdefinierten geschichteten Kanals besteht im Erstellen einer Implementierung von <xref:System.ServiceModel.Channels.IChannelFactory> für Clientkanäle und von <xref:System.ServiceModel.Channels.IChannelListener> für Dienstkanäle.  
  
 Diese Klassen nehmen eine innere Factory und einen inneren Listener und delegieren alle Aufrufe außer den `OnCreateChannel`- und `OnAcceptChannel`-Aufrufen an die innere Factory und den inneren Listener.  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{ 
    //... 
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{ 
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a>Hinzufügen eines Bindungselements  
 Das Beispiel definiert ein benutzerdefiniertes Bindungselement: `InterceptingBindingElement`. `InterceptingBindingElement` nimmt eine `ChannelMessageInterceptor` als Eingabe an und verwendet diese `ChannelMessageInterceptor` zum Bearbeiten von Nachrichten, die Sie durchlaufen. Dies ist die einzige Klasse, die öffentlich sein muss. Die Factory, der Listener und die Kanäle können alle interne Implementierungen der öffentlichen Laufzeit-Schnittstellen sein.  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a>Hinzufügen von Konfigurationsunterstützung  
 Die Bibliothek definiert einen Konfigurationsabschnittshandler als Bindungselementerweiterungs-Abschnitt, um die Bindungskonfiguration zu integrieren. Die Client- und Serverkonfigurationsdateien müssen die Bindungselementerweiterung auf dem Konfigurationssystem registrieren. Implementierer, die ihr Bindungselement auf dem Konfigurationssystem verfügbar machen möchten, können von dieser Klasse ableiten.  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement 
{ 
    //... 
}
```  
  
## <a name="adding-policy"></a>Hinzufügen einer Richtlinie  
 Zum Integrieren mit unserem Richtliniensystem implementiert `InterceptingBindingElement` IPolicyExportExtension, um die Teilnahme beim Generieren der Richtlinie zu signalisieren. Damit das Importieren einer Richtlinie auf einem generierten Client unterstützt wird, kann der Benutzer eine abgeleitete Klasse von `InterceptingBindingElementImporter` registrieren und `CreateMessageInterceptor`() überschreiben, um die richtlinienfähige `ChannelMessageInterceptor`-Klasse zu generieren.  
  
## <a name="example-droppable-message-inspector"></a>Beispiel: Zu verwerfender Nachrichteninspektor  
 Das Beispiel umfasst eine Beispielimplementierung von `ChannelMessageInspector`, der Meldungen verwirft.  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 Sie rufen es wie folgt über die Konfiguration auf:  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"   
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 Sowohl der Client als auch der Server verwenden den neu erstellten Konfigurationsabschnitt, um die benutzerdefinierten Factorys in die unterste Schicht ihrer Laufzeit-Kanalstapel (über der Transportebene) einzufügen.  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 Der Client verwendet die `MessageInterceptor`-Bibliothek, um einen benutzerdefinierten Header für Meldungen mit geraden Zahlen hinzuzufügen. Der Dienst hingegen verwendet die `MessageInterceptor`-Bibliothek, um alle Meldungen zu verwerfen, die diesen Header nicht enthalten.  
  
 Nach Ausführen des Diensts und anschließendem Ausführen des Clients sollte folgende Clientausgabe angezeigt werden:  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 Der Client meldet 10 verschiedene Windgeschwindigkeiten an den Dienst, aber nur die Hälfte der Meldungen wird mit dem speziellen Header gekennzeichnet.  
  
 Auf dem Dienst sollten Sie die folgende Ausgabe erhalten:  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
3. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.  
  
4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5. Führen Sie zuerst "Service.exe" und dann "Client.exe" aus, und sehen Sie sich die Ausgabe in beiden Konsolenfenstern an.  
