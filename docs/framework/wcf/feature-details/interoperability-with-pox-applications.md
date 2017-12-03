---
title: "Interoperabilität mit POX-Anwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf05e3327d7c99d333ab4be045e3f72e6f2a8a3f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="interoperability-with-pox-applications"></a>Interoperabilität mit POX-Anwendungen
"Plain Old XML" (POX)-Anwendungen kommunizieren, indem Sie den Austausch von unformatierte HTTP-Nachrichten, die nur XML-Anwendungsdaten enthalten, die nicht in einen SOAP-Umschlag eingeschlossen ist. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kann Dienste und Clients bereitstellen, die POX-Nachrichten verwenden. Beim Dienst kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] für die Implementierung von Diensten verwendet werden, die Endpunkte wie Webbrowser und Skriptsprachen, mit denen POX-Nachrichten gesendet und empfangen werden können, für Clients verfügbar machen. Auf dem Client kann das Programmiermodell von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Implementierung von Clients, die mit POX-basierten Diensten kommunizieren, herangezogen werden.  
  
> [!NOTE]
>  Dieses Dokument wurde ursprünglich für [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&#160;3.0 geschrieben.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]&amp;#160;3.5 verfügt über intergrierte Unterstützung für die Arbeit mit POX-Anwendungen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]finden Sie unter [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
  
## <a name="pox-programming-with-wcf"></a>POX-Programmierung mit WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]Dienste, die für die Kommunikation über HTTP unter Verwendung von POX-Nachrichten mithilfe einer [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
```xml  
<customBinding>  
   <binding name="poxServerBinding">  
       <textMessageEncoding messageVersion="None" />  
       <httpTransport />  
   </binding>  
</customBinding>  
```  
  
 Diese benutzerspezifische Bindung enthält zwei Elemente:  
  
-   Die [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) und  
  
-   Die [ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
 Der standardmäßige Textnachrichtenencoder von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist spezifisch für die Verwendung des <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Werts konfiguriert, wodurch XML-Nachrichten ohne SOAP-Envelope verarbeitet werden können.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients, die über HTTP unter Verwendung von POX-Nachrichten kommunizieren, verwenden eine ähnliche Bindung (wie im folgenden imperativen Code zu sehen ist):  
  
```  
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
  
 Da bei POX-Nachrichten keine SOAP-Header für die Übermittlung wichtiger Protokollinformationen verwendet werden, müssen POX-Clients und -Dienste häufig Teile der zugrunde liegenden HTTP-Anforderung, die zum Senden und Empfangen einer Nachricht verwendet wird, manipulieren. HTTP-spezifische Protokollinformationen wie HTTP-Header und Statuscodes werden im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Programmiermodell durch zwei Klassen bereitgestellt:  
  
-   <xref:System.ServiceModel.Channels.HttpRequestMessageProperty>, die Informationen zur HTTP-Anforderung wie die HTTP-Methode und Anforderungsheader enthält.  
  
-   <xref:System.ServiceModel.Channels.HttpResponseMessageProperty>, die Informationen zur HTTP-Antwort enthält wie den HTTP-Statuscode und die Statusbeschreibung sowie alle HTTP-Antwortheader.  
  
 Das folgende Codebeispiel zeigt, wie Sie eine HTTP GET-Anforderungsnachricht mit der Adresse http://localhost:8100/customers erstellen können:  
  
```  
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );  
request.Headers.To = "http://localhost:8100/customers";  
  
HttpRequestMessageProperty property = new HttpRequestMessageProperty();  
property.Method = "GET";  
property.SuppressEntityBody = true;  
request.Properties.Add( HttpRequestMessageProperty.Name, property );  
```  
  
 Zuerst wird die leere Anforderung <xref:System.ServiceModel.Channels.Message> durch Aufruf von <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29> erstellt. Der <xref:System.ServiceModel.Channels.MessageVersion.None%2A>-Parameter zeigt an, dass kein SOAP-Envelope erforderlich ist. Der <xref:System.String.Empty>-Parameter wird als Aktion übergeben. Anschließend wird die Adresse für die Anforderungsnachricht angegeben, indem im <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Header der gewünschte URI festgelegt wird. Dann wird eine <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> erstellt. <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> wird auf die HTTP GET-Methode festgelegt, und für <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> wird der Wert `true` festgelegt, um anzuzeigen, dass keine Daten im Text der ausgehenden HTTP-Anforderungsnachricht gesendet werden sollen. Anschließend wird noch die Anforderungseigenschaft zur <xref:System.ServiceModel.Channels.Message.Properties%2A>-Auflistung der Anforderungsnachricht hinzugefügt, damit gesteuert werden kann, auf welche Weise der HTTP-Transport die Anforderung sendet. Die Nachricht kann nun über eine geeignete Instanz von <xref:System.ServiceModel.Channels.IRequestChannel> gesendet werden.  
  
 Auf ähnliche Weise kann beim Dienst die <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> aus der eingehenden Nachricht extrahiert und eine Antwort erstellt werden.
