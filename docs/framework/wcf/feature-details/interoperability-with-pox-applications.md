---
title: Interoperabilität mit POX-Anwendungen
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: b7fdb4e16bce52025515ced065d0f48cffb7fa3f
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850080"
---
# <a name="interoperability-with-pox-applications"></a>Interoperabilität mit POX-Anwendungen

"Plain Old XML" (POX)-Anwendungen kommunizieren, indem Sie den Austausch von unformatierte HTTP-Nachrichten, die nur XML-Anwendungsdaten enthalten, die nicht in einem SOAP-Umschlag eingeschlossen ist. Windows Communication Foundation (WCF) bieten, die Dienste und Clients, die POX-Nachrichten verwenden. Für den Dienst kann WCF verwendet werden, Implementieren von Diensten, die Endpunkte für Clients, z. B. Webbrowser verfügbar zu machen und Skriptsprachen, mit die POX-Nachrichten senden und empfangen. Auf dem Client kann die WCF-Programmiermodell verwendet werden, zur Implementierung von Clients, die mit POX-basierten Diensten kommunizieren.  
  
> [!NOTE]
> Dieses Dokument wurde ursprünglich für [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&#160;3.0 geschrieben.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&amp;#160;3.5 verfügt über intergrierte Unterstützung für die Arbeit mit POX-Anwendungen. Weitere Informationen finden Sie unter [WCF-HTTP-Webprogrammierungsmodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).
  
## <a name="pox-programming-with-wcf"></a>POX-Programmierung mit WCF

WCF-Dienste, die Kommunikation über HTTP unter Verwendung von POX-Nachrichten verwenden eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

Diese benutzerspezifische Bindung enthält zwei Elemente:

- [\<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

- [\<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)

Der Standard, speziell für die Verwendung konfiguriert Textnachrichtenencoder WCF, die <xref:System.ServiceModel.Channels.MessageVersion.None%2A> -Wert, der kann zum Verarbeiten von XML-Nutzlasten für Nachrichten, die nicht eingetroffen in einen SOAP-Umschlag eingeschlossen.

WCF-Clients, die über HTTP unter Verwendung von POX-Nachrichten kommunizieren, verwenden eine ähnliche Bindung (siehe folgenden imperativen Code).

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

Da bei POX-Nachrichten keine SOAP-Header für die Übermittlung wichtiger Protokollinformationen verwendet werden, müssen POX-Clients und -Dienste häufig Teile der zugrunde liegenden HTTP-Anforderung, die zum Senden und Empfangen einer Nachricht verwendet wird, manipulieren. HTTP-spezifische Protokollinformationen wie HTTP-Header und Statuscodes werden in der WCF-Programmiermodell über zwei Klassen aufgeführt:

- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, die Informationen zur HTTP-Anforderung wie die HTTP-Methode und Anforderungsheader enthält.

- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, die Informationen zur HTTP-Antwort enthält wie den HTTP-Statuscode und die Statusbeschreibung sowie alle HTTP-Antwortheader.
  
Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine HTTP GET-Request-Nachricht zu erstellen, die an adressiert wird `http://localhost:8100/customers`.

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
