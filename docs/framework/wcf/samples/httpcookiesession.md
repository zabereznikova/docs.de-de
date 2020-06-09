---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: 8dba147ace7ada221b5d274cd233e4b9618835d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585129"
---
# <a name="httpcookiesession"></a>HttpCookieSession
In diesem Beispiel wird das Erstellen eines benutzerdefinierten Protokollkanals für die Verwendung von HTTP-Cookies für die Sitzungsverwaltung veranschaulicht. Dieser Kanal ermöglicht die Kommunikation zwischen Windows Communication Foundation (WCF)-Diensten und ASMX-Clients oder zwischen WCF-Clients und ASMX-Diensten.  
  
 Wenn ein Client eine Webmethode in einem Sitzungs basierten ASMX-Webdienst aufruft, bewirkt die ASP.net-Engine Folgendes:  
  
- Generiert eine eindeutige ID (Sitzungs-ID).  
  
- Generiert das Sitzungsobjekt und ordnet es der eindeutigen ID zu.  
  
- Fügt die eindeutige ID dem HTTP-Antwortheader Set-Cookie hinzu und sendet diesen an den Client.  
  
- Identifiziert den Client in nachfolgenden Aufrufen auf Grundlage der an ihn gesendeten Sitzungs-ID.  
  
 Der Client schließt diese Sitzungs-ID in nachfolgenden Anforderungen an den Server ein. Der Server lädt mithilfe der Sitzungs-ID vom Client das entsprechende Sitzungsobjekt für den aktuellen HTTP-Kontext.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a>HttpCookieSession-Nachrichtenaustauschmuster für Kanal  
 In diesem Beispiel werden Sitzungen für ASMX-ähnliche Szenarios aktiviert. Unten im Kanalstapel befindet sich der HTTP-Transport, der <xref:System.ServiceModel.Channels.IRequestChannel> und <xref:System.ServiceModel.Channels.IReplyChannel> unterstützt. Der Kanal stellt Sitzungen für die höheren Ebenen des Kanalstapels bereit. Im Beispiel werden zwei Kanäle implementiert, die Sitzungen unterstützen (<xref:System.ServiceModel.Channels.IRequestSessionChannel> und <xref:System.ServiceModel.Channels.IReplySessionChannel>).  
  
## <a name="service-channel"></a>Dienstkanal  
 Im Beispiel wird ein Dienstkanal in der `HttpCookieReplySessionChannelListener`-Klasse bereitgestellt. Diese Klasse implementiert die <xref:System.ServiceModel.Channels.IChannelListener>-Schnittstelle und konvertiert den <xref:System.ServiceModel.Channels.IReplyChannel>-Kanal weiter unten im Kanalstapel in <xref:System.ServiceModel.Channels.IReplySessionChannel>. Dieser Prozess kann folgendermaßen unterteilt werden:  
  
- Wenn der Kanallistener geöffnet wird, akzeptiert er einen inneren Kanal vom inneren Listener. Da es sich bei dem inneren Listener um einen Datagrammlistener handelt und die Lebensdauer eines akzeptierten Kanals unabhängig von der Lebensdauer des Listeners ist, kann der innere Listener geschlossen und nur der innere Kanal beibehalten werden.  
  
    ```csharp  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- Wenn der Prozess zum Öffnen abgeschlossen ist, wird eine Nachrichtenschleife zum Empfangen von Nachrichten vom inneren Kanal eingerichtet.  
  
    ```csharp  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       this.completeReceiveCallback ??= new WaitCallback(CompleteReceiveCallback);
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- Wenn eine Nachricht eingeht, prüft der Dienstkanal die Sitzungs-ID und führt ein De-Multiplexing für den entsprechenden Sitzungskanal durch. Der Kanallistener verwaltet ein Wörterbuch, das die Sitzungs-IDs den Sitzungskanalinstanzen zuordnet.  
  
    ```csharp  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 Die- `HttpCookieReplySessionChannel` Klasse implementiert <xref:System.ServiceModel.Channels.IReplySessionChannel> . In höheren Ebenen des Kanalstapels wird die <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>-Methode aufgerufen, um Anforderungen für diese Sitzung zu lesen. Jeder Sitzungskanal verfügt über eine private Meldungswarteschlange, die vom Dienstkanal aufgefüllt wird.  
  
```csharp  
InputQueue<RequestContext> requestQueue;  
```  
  
 Wenn die <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A>-Methode aufgerufen wird und sich keine Meldungen in der Meldungswarteschlange befinden, wartet der Kanal für einen angegebenen Zeitraum und beendet sich dann selbst. Dadurch werden die Sitzungskanäle bereinigt, die für nicht-WCF-Clients erstellt wurden.  
  
 Mit `channelMapping` wird `ReplySessionChannels` nachverfolgt. Außerdem wird der zugrunde liegende `innerChannel` erst geschlossen, wenn alle akzeptierten Kanäle geschlossen wurden. So kann `HttpCookieReplySessionChannel` über die Lebensdauer von `HttpCookieReplySessionChannelListener` hinaus vorhanden sein. Außerdem besteht nicht die Gefahr, dass der Listener durch die Garbage Collection entfernt wird, da die akzeptierten Kanäle über den `OnClosed`-Rückruf einen Verweis auf den Listener beibehalten.  
  
## <a name="client-channel"></a>Clientkanal  
 Der entsprechende Clientkanal befindet sich in der `HttpCookieSessionChannelFactory`-Klasse. Bei der Kanalerstellung schließt die Kanalfactory den inneren Anforderungskanal mit einem `HttpCookieRequestSessionChannel` ein. Die `HttpCookieRequestSessionChannel`-Klasse leitet die Aufrufe des zugrunde liegenden Anforderungskanals weiter. Wenn der Client den Proxy schließt, sendet `HttpCookieRequestSessionChannel` eine Meldung an den Dienst, mit der angegeben wird, dass der Kanal geschlossen wird. So kann der Dienstkanalstapel den verwendeten Sitzungskanal ordnungsgemäß beenden.  
  
## <a name="binding-and-binding-element"></a>Bindung und Bindungselement  
 Nachdem Sie den Dienst und die Client Kanäle erstellt haben, besteht der nächste Schritt darin, Sie in die WCF-Laufzeit zu integrieren. Kanäle werden über Bindungen und Bindungs Elemente für WCF verfügbar gemacht. Eine Bindung besteht aus einem oder mehreren Bindungselementen. WCF bietet mehrere System definierte Bindungen. beispielsweise BasicHttpBinding oder WSHttpBinding. Die `HttpCookieSessionBindingElement`-Klasse enthält die Implementierung des Bindungselements. Sie überschreibt die Methoden zur Kanallistener- und Kanalfactoryerstellung, um die erforderlichen Instanziierungen des Kanallisteners und der Kanalfactory auszuführen.  
  
 Im Beispiel werden Richtlinienassertionen für die Dienstbeschreibung verwendet. So können im Beispiel die Kanalanforderungen für andere Clients veröffentlicht werden, die den Dienst verwenden können. Dieses Bindungselement veröffentlicht beispielsweise Richtlinienassertionen, damit potenzielle Clients wissen, dass Sitzungen unterstützt werden. Da im Beispiel die `ExchangeTerminateMessage`-Eigenschaft in der Bindungselementkonfiguration aktiviert wird, werden die erforderlichen Assertionen hinzugefügt, um zu zeigen, dass der Dienst eine zusätzliche Meldungsaustauschaktion zum Beenden der Sitzungskommunikation unterstützt. Clients können diese Aktion dann verwenden. Im folgenden WSDL-Code werden die aus `HttpCookieSessionBindingElement` erstellten Richtlinienassertionen veranschaulicht.  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Die `HttpCookieSessionBinding`-Klasse ist eine vom System bereitgestellte Bindung, die das zuvor beschriebene Bindungselement verwendet.  
  
## <a name="adding-the-channel-to-the-configuration-system"></a>Hinzufügen des Kanals zum Konfigurationssystem  
 Im Beispiel werden zwei Klassen bereitgestellt, die den Beispielkanal durch Konfiguration verfügbar machen. Die erste ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> für das `HttpCookieSessionBindingElement`. Dem `HttpCookieSessionBindingConfigurationElement`, das sich von <xref:System.ServiceModel.Configuration.StandardBindingElement> herleitet, wird der Großteil der Implementierung übertragen. `HttpCookieSessionBindingConfigurationElement` verfügt über Eigenschaften, die den Eigenschaften von `HttpCookieSessionBindingElement` entsprechen.  
  
### <a name="binding-element-extension-section"></a>Abschnitt für Bindungselementerweiterungen  
 Der Abschnitt `HttpCookieSessionBindingElementSection` ist ein <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>, das die `HttpCookieSessionBindingElement` für das Konfigurationssystem verfügbar macht. Mit wenigen Überschreibungen werden der Konfigurationsabschnittsname, der Typ des Bindungselements und das Erstellen des Bindungselements definiert. Danach kann der Erweiterungsabschnitt wie folgt in einer Konfigurationsdatei registriert werden:  
  
```xml  
<configuration>
    <system.serviceModel>
      <extensions>
        <bindingElementExtensions>
          <add name="httpCookieSession"
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,
                    HttpCookieSessionExtension, Version=1.0.0.0,
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>
    </system.serviceModel>
</configuration>  
```  
  
## <a name="test-code"></a>Testcode  
 Testcode für die Verwendung dieses Beispieltransports ist in den Client- und Dienstverzeichnissen verfügbar. Sie besteht aus zwei Tests – bei einem Test wird eine Bindung verwendet `allowCookies` , bei `true` der auf dem Client auf festgelegt ist. Im zweiten Test wird das explizite Herunterfahren (mit abschließenden Meldungsaustausch) für die Bindung aktiviert.  
  
 Wenn Sie das Beispiel ausführen, sollten Sie folgende Ausgabe erhalten:  
  
```console  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
3. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.  
  
4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
