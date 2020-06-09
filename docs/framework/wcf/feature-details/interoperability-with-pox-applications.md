---
title: Interoperabilität mit POX-Anwendungen
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: 64a6d850a32b14bc60cd43466e04b53a7a39be81
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579266"
---
# <a name="interoperability-with-pox-applications"></a>Interoperabilität mit POX-Anwendungen

"Plain Old XML" (POX)-Anwendungen kommunizieren durch Austauschen von unformatierten HTTP-Nachrichten, die nur XML-Anwendungsdaten enthalten, die nicht in einem SOAP-Umschlag eingeschlossen sind. Windows Communication Foundation (WCF) kann sowohl Dienste als auch Clients bereitstellen, die POX-Nachrichten verwenden. Auf dem-Dienst kann WCF verwendet werden, um Dienste zu implementieren, die Endpunkte für Clients verfügbar machen, z. b. Webbrowser und Skriptsprachen, die POX-Nachrichten senden und empfangen. Auf dem Client kann das WCF-Programmiermodell verwendet werden, um Clients zu implementieren, die mit POX-basierten Diensten kommunizieren.  
  
> [!NOTE]
> Dieses Dokument wurde ursprünglich für das .NET Framework 3,0 geschrieben.  .NET Framework 3,5 verfügt über eine integrierte Unterstützung für die Arbeit mit POX-Anwendungen. Weitere Informationen finden Sie unter [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md).
  
## <a name="pox-programming-with-wcf"></a>POX-Programmierung mit WCF

WCF-Dienste, die mithilfe von POX-Nachrichten über HTTP kommunizieren, verwenden [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

Diese benutzerspezifische Bindung enthält zwei Elemente:

- [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md)

- [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md)

Der standardmäßige WCF-Text Nachrichten Encoder ist speziell für die Verwendung des- <xref:System.ServiceModel.Channels.MessageVersion.None%2A> Werts konfiguriert, mit dem XML-Nachrichten Nutzlasten verarbeitet werden können, die nicht in einem SOAP-Umschlag umschließt werden.

WCF-Clients, die mithilfe von POX-Nachrichten über HTTP kommunizieren, verwenden eine ähnliche Bindung (in folgendem imperativen Code gezeigt).

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

Da POX-Clients die URIs, an die Nachrichten gesendet werden, explizit angeben müssen, muss das <xref:System.ServiceModel.Channels.HttpTransportBindingElement> in der Regel so konfiguriert werden, dass eine manuelle Adressierung möglich ist. Hierfür wird im Element die <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A>-Eigenschaft auf `true` festgelegt. Auf diese Weise kann die Adresse für die Nachricht explizit über Anwendungscode angegeben werden, und es muss nicht jedes Mal, wenn eine Anwendung eine Nachricht an einen anderen HTTP-URI sendet, eine neue <xref:System.ServiceModel.ChannelFactory> erstellt werden.

Da bei POX-Nachrichten keine SOAP-Header für die Übermittlung wichtiger Protokollinformationen verwendet werden, müssen POX-Clients und -Dienste häufig Teile der zugrunde liegenden HTTP-Anforderung, die zum Senden und Empfangen einer Nachricht verwendet wird, manipulieren. HTTP-spezifische Protokollinformationen, wie z. b. HTTP-Header und Statuscodes, werden im WCF-Programmiermodell über zwei Klassen angezeigt:

- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, die Informationen zur HTTP-Anforderung wie die HTTP-Methode und Anforderungsheader enthält.

- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, die Informationen zur HTTP-Antwort enthält wie den HTTP-Statuscode und die Statusbeschreibung sowie alle HTTP-Antwortheader.
  
Im folgenden Codebeispiel wird gezeigt, wie eine HTTP GET-Anforderungs Nachricht erstellt wird, die an adressiert wird `http://localhost:8100/customers` .

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

Zuerst wird die leere Anforderung <xref:System.ServiceModel.Channels.Message> durch Aufruf von <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29> erstellt. Der <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Parameter zeigt an, dass kein SOAP-Envelope erforderlich ist. Der <xref:System.String.Empty>-Parameter wird als Aktion übergeben. Anschließend wird die Adresse für die Anforderungsnachricht angegeben, indem im <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Header der gewünschte URI festgelegt wird. Dann wird eine <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> erstellt. <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> wird auf die HTTP GET-Methode festgelegt, und für <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> wird der Wert `true` festgelegt, um anzuzeigen, dass keine Daten im Text der ausgehenden HTTP-Anforderungsnachricht gesendet werden sollen. Anschließend wird noch die Anforderungseigenschaft zur <xref:System.ServiceModel.Channels.Message.Properties%2A>-Auflistung der Anforderungsnachricht hinzugefügt, damit gesteuert werden kann, auf welche Weise der HTTP-Transport die Anforderung sendet. Die Nachricht kann nun über eine geeignete Instanz von <xref:System.ServiceModel.Channels.IRequestChannel> gesendet werden.

Auf ähnliche Weise kann beim Dienst die <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> aus der eingehenden Nachricht extrahiert und eine Antwort erstellt werden.
