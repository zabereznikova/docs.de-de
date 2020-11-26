---
title: WSDL und Richtlinie
ms.date: 03/30/2017
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
ms.openlocfilehash: 123a878e90ee9099b009985a5e79155e8b1cd097
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238339"
---
# <a name="wsdl-and-policy"></a>WSDL und Richtlinie

Dieses Thema behandelt Windows Communication Foundation (WCF) WSDL 1,1, WS-Policy und WS-PolicyAttachment Implementierungsdetails sowie weitere WS-Policy Assertionen und WSDL 1,1-Erweiterungen, die von WCF eingeführt wurden.  
  
 WCF implementiert WS-Policy und WS-PolicyAttachment Spezifikationen, die an W3C übermittelt wurden, mit Einschränkungen und in diesem Dokument beschriebenen Erläuterungen.  
  
 Dieses Dokument verwendet die in der folgenden Tabelle angeführten Präfixe und Namespaces.  
  
|Präfix|Namespace|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|`http://schemas.xmlsoap.org/ws/2004/09/policy`|  
|wsp (WS-Policy 1.5)|`http://www.w3.org/ns/ws-policy`|  
|http|`http://schemas.microsoft.com/ws/06/2004/policy/http`|  
|msmq|`http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq`|  
|msf|`http://schemas.microsoft.com/ws/2006/05/framing/policy`|  
|mssp|`http://schemas.microsoft.com/ws/2005/07/securitypolicy`|  
|msc|`http://schemas.microsoft.com/ws/2005/12/wsdl/contract`|  
|cdp|`http://schemas.microsoft.com/net/2006/06/duplex`|  
  
## <a name="wcf-wsdl11-extensions"></a>WCF WSDL 1.1-Erweiterungen  

 WCF verwendet die folgenden WSDL 1.1-Erweiterungen, um die Anforderungen an die Vertrags Sitzung zu beschreiben.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 xs: Boolean, gibt an, dass dieser Vorgang eine WCF-Sitzung initiiert. der Standardwert ist `false` .  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 xs: Boolean, gibt an, dass dieser Vorgang eine WCF-Sitzung beendet. der Standardwert ist `false` .  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, gibt an, dass dieser Vertrag zum Erstellen eine Sitzung erfordert.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>SOAP 1.x HTTP-Bindungstransport-URIs  

 WCF verwendet die folgenden URIs, um Transporte anzugeben, die für die Bindungs Erweiterungs Elemente WSDL 1,1, SOAP 1,1 und SOAP 1,2 verwendet werden sollen.  
  
|Transport|URI|  
|---------------|---------|  
|HTTP|`http://schemas.xmlsoap.org/soap/http`|  
|TCP|`http://schemas.microsoft.com/soap/tcp`|  
|MSMQ|`http://schemas.microsoft.com/soap/msmq`|  
|Named Pipes|`http://schemas.microsoft.com/soap/named-pipe`|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Von WCF implementierte Richtlinienassertionen  

 Zusätzlich zu den in den Webdienst Spezifikationen (WS-*) eingeführten und in anderen Abschnitten dieses Dokuments erwähnten Richtlinien Assertionen implementiert WCF die folgenden Richtlinien Assertionen.  
  
|Richtlinienassertion|Richtliniensubjekt|BESCHREIBUNG|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Endpunkt|Endpunkt verwendet die HTTP-Standardauthentifizierung.|  
|http:HttpDigestAuthentication|Endpunkt|Endpunkt verwendet die HTTP-Hashwertauthentifizierung.|  
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
|mssp:RsaToken|geschachtelt|RSA-Schlüsseltokenassertion. Diese Anforderung wird in der Regel durch einen als Teil der Schlüsselinformationen in einer unterzeichnenden Signatur direkt serialisierten RSA-Schlüssel erfüllt.|  
|mssp:SslContextToken|geschachtelt|Erfordert, dass ein mit binärem TLS-Handshake mit WS-Trust abgerufener SecurityContextToken verwendet wird. Geschachtelte Assertionen umfassen: sp:RequireDerivedKeys, mssp:MustNotSendCancel, mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|geschachtelt|Gibt eine Anforderung an, dass Anforderungssicherheitstoken (Request Security Token, RST)-Anforderungsnachrichten [WS-Trust], die die Cancel-Bindung [WS-Trust, WS-SC] verwenden, nicht an den Aussteller eines bestimmten SecurityContextToken gesendet werden. Wenn diese Assertion vorhanden ist, dürfen solche Anforderungsnachrichten nicht an den Aussteller gesendet werden. Wenn diese Assertion nicht vorhanden ist, können solche Anforderungsnachrichten an den Aussteller gesendet werden.|  
|mssp:RequireClientCertificate|geschachtelt|Dieses optionale Element gibt die Anforderung an, dass ein Clientzertifikat als Teil des TLSNEGO-Protokolls bereitgestellt wird. Wenn diese Assertion vorhanden ist, muss ein Clientzertifikat bereitgestellt werden. Wenn diese Assertion nicht vorhanden ist, darf kein Clientzertifikat bereitgestellt werden. Diese Assertion darf nicht außerhalb von mssp:SslContextToken verwendet werden.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzerdefinierte WSDL-Veröffentlichung](../samples/custom-wsdl-publication.md)
- [Vorgehensweise: Exportieren von benutzerdefinierten WSDL-Informationen](../extending/how-to-export-custom-wsdl.md)
- [Vorgehensweise: Importieren von benutzerdefinierten WSDL-Informationen](../extending/how-to-import-custom-wsdl.md)
