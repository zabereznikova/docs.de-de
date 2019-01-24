---
title: WSDL und Richtlinie
ms.date: 03/30/2017
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
ms.openlocfilehash: 1e6b315c1830602e72b4b498cd38eed8428bc5ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741430"
---
# <a name="wsdl-and-policy"></a>WSDL und Richtlinie
Dieses Thema behandelt die Windows Communication Foundation (WCF)-WSDL 1.1, WS-Policy und WS-PolicyAttachment-Implementierungsdetails, sowie zusätzliche WS-Richtlinienassertionen und WSDL 1.1-Erweiterungen, die von WCF eingeführt.  
  
 WCF implementiert die WS-Policy und WS-PolicyAttachment-Spezifikationen, die mit der in diesem Dokument beschriebenen Einschränkungen und klarstellungen an W3C gesendet.  
  
 Dieses Dokument verwendet die in der folgenden Tabelle angeführten Präfixe und Namespaces.  
  
|Präfix|Namespace|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|http://schemas.xmlsoap.org/ws/2004/09/policy|  
|wsp (WS-Policy 1.5)|http://www.w3.org/ns/ws-policy|  
|http|http://schemas.microsoft.com/ws/06/2004/policy/http|  
|msmq|http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq|  
|msf|http://schemas.microsoft.com/ws/2006/05/framing/policy|  
|mssp|http://schemas.microsoft.com/ws/2005/07/securitypolicy|  
|msc|http://schemas.microsoft.com/ws/2005/12/wsdl/contract|  
|cdp|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="wcf-wsdl11-extensions"></a>WCF WSDL 1.1-Erweiterungen  
 WCF verwendet die folgenden WSDL 1.1-Erweiterungen um zu beschreiben.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 xs: Boolean, gibt an, dass es sich bei diesem Vorgang eine WCF-Sitzung initiiert; Der Standardwert ist `false`.  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 xs: Boolean, gibt an, dass es sich bei diesem Vorgang eine WCF-Sitzung beendet wird; Der Standardwert ist `false`.  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, gibt an, dass dieser Vertrag zum Erstellen eine Sitzung erfordert.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>SOAP 1.x HTTP-Bindungstransport-URIs  
 WCF verwendet die folgenden URIs Transporten für WSDL 1.1-, SOAP 1.1- und SOAP 1.2-bindungserweiterungselemente verwendet werden soll.  
  
|Transport|URI|  
|---------------|---------|  
|HTTP|http://schemas.xmlsoap.org/soap/http|  
|TCP|http://schemas.microsoft.com/soap/tcp|  
|MSMQ|http://schemas.microsoft.com/soap/msmq|  
|Benannte Pipes|http://schemas.microsoft.com/soap/named-pipe|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Von WCF implementierte Richtlinienassertionen  
 Zusätzlich zu Richtlinienassertionen eingeführt, die in den Webdienstspezifikationen (ws-*) und in anderen Abschnitten dieses Handbuchs erwähnt, implementiert WCF die folgenden Richtlinienassertionen.  
  
|Richtlinienassertion|Richtliniensubjekt|Beschreibung|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Endpunkt|Endpunkt verwendet die HTTP-Standardauthentifizierung.|  
|http:HttpDigestAuthentication|Endpunkt|Endpunkt verwendet die HTTP-Digestauthentifizierung.|  
|http:HttpNegotiateAuthentication|Endpunkt|Endpunkt verwendet die HTTP-Negotiate-Authentifizierung.|  
|http:HttpNtlmAuthentication|Endpunkt|Endpunkt verwendet die HTTP-NTLM-Authentifizierung.|  
|msf:Streamed|Endpunkt|Endpunkt verwendet Stream-Nachrichtenrahmen. Diese Assertion wird mit dem für Transporte wie TCP bereitgestellten Message Framing-Protokoll und benannte Pipes verwendet.|  
|msf:SslTransportSecurity|Endpunkt|Endpunkt verwendet TLS (Transport Layer Security) mit Nachrichtenrahmen.|  
|msf:WindowsTransportSecurity|Endpunkt|Endpunkt verwendet SPNEGO (Security Provider Negotiation) mit Nachrichtenrahmen.|  
|msmq:MsmqBestEffort|Endpunkt|MSMQ mit Best-Effort-Garantien.|  
|msmq:MsmqSession|Endpunkt|MSMQ mit Sitzungsgarantien.|  
|msmq:MsmqVolatile|Endpunkt|MSMQ Volatile.|  
|msmq:Authenticated|Endpunkt|Die Authentifizierung wird mit dem MSMQ-Transport verwendet.|  
|msmq:WindowsDomain|Endpunkt|MSMQ verwendet die Windows-Domänenauthentifizierung.|  
|cdp:CompositeDuplex|Endpunkt|Endpunkt verwendet zwei separate umgekehrte Transportverbindungen für ein- und ausgehende Nachrichten.|  
|mssp:RsaToken|Geschachtelt|RSA-Schlüsseltokenassertion. Diese Anforderung wird in der Regel durch einen als Teil der Schlüsselinformationen in einer unterzeichnenden Signatur direkt serialisierten RSA-Schlüssel erfüllt.|  
|mssp:SslContextToken|Geschachtelt|Erfordert, dass ein mit binärem TLS-Handshake mit WS-Trust abgerufener SecurityContextToken verwendet wird. Geschachtelte Assertionen umfassen: sp:RequireDerivedKeys, mssp:MustNotSendCancel, mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|Geschachtelt|Gibt eine Anforderung an, dass Anforderungssicherheitstoken (Request Security Token, RST)-Anforderungsnachrichten [WS-Trust], die die Cancel-Bindung [WS-Trust, WS-SC] verwenden, nicht an den Aussteller eines bestimmten SecurityContextToken gesendet werden. Wenn diese Assertion vorhanden ist, dürfen solche Anforderungsnachrichten nicht an den Aussteller gesendet werden. Wenn diese Assertion nicht vorhanden ist, können solche Anforderungsnachrichten an den Aussteller gesendet werden.|  
|mssp:RequireClientCertificate|Geschachtelt|Dieses optionale Element gibt die Anforderung an, dass ein Clientzertifikat als Teil des TLSNEGO-Protokolls bereitgestellt wird. Wenn diese Assertion vorhanden ist, muss ein Clientzertifikat bereitgestellt werden. Wenn diese Assertion nicht vorhanden ist, darf kein Clientzertifikat bereitgestellt werden. Diese Assertion darf nicht außerhalb von mssp:SslContextToken verwendet werden.|  
  
## <a name="see-also"></a>Siehe auch
- [Benutzerdefinierte WSDL-Veröffentlichung](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)
- [Vorgehensweise: Exportieren von benutzerdefinierter WSDL](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)
- [Vorgehensweise: Benutzerdefinierte WSDL importieren](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
