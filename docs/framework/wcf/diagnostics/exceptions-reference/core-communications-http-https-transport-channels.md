---
title: 'Kernkommunikation: HTTP-HTTPS-Transportkanäle'
ms.date: 03/30/2017
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
ms.openlocfilehash: fbdb5b350425aad7108402dec939f036e971d053
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473326"
---
# <a name="core-communications-httphttps-transport-channels"></a>Kernkommunikation: HTTP/HTTPS-Transportkanäle
In diesem Thema sind alle von Windows Communication Foundation (WCF)-HTTP/HTTPS-Transportkanälen generierte Ausnahmen aufgeführt.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|Die angegebene Identitätswechselebene wurde angegeben. Die HTTP-Digestauthentifizierung kann Identitätswechselebenen jedoch nur in Kombination mit expliziten Anmeldeinformationen unterstützen.|  
|FramingContentTypeMismatch|Der angegebene Inhaltstyp wurde vom angegebenen Dienst nicht unterstützt. Möglicherweise besteht keine Übereinstimmung zwischen Client- und Dienstbindung.|  
|Hosting_SslSettingsMisconfigured|Die Secure Sockets Layer-Einstellungen für den angegebenen Dienst stimmen nicht mit den Einstellungen der Internet Information Services überein.|  
|HttpAuthSchemeAndClientCert|Die Konfiguration der HTTPS-Listenerfactory erfordert ein Clientzertifikat und das angegebene Authentifizierungsschema. Es kann jedoch immer nur jeweils eine Form der Clientauthentifizierung erforderlich sein.|  
|HttpReceiveFailure|Fehler beim Empfangen der HTTP-Antwort für das angegebene Element. Möglicherweise verwendet die Dienstendpunktbindung kein HTTP-Protokoll. Eine andere mögliche Ursache ist, dass der HTTP-Anforderungskontext vom Server abgebrochen wird (vermutlich auf das Herunterfahren eines Diensts zurückzuführen). Weitere Informationen finden Sie in den Serverprotokollen.|  
|HttpRegistrationAccessDenied|HTTP kann die angegebene URL nicht registrieren. Der Prozess verfügt nicht über die Zugriffsrechte für diesen Namespace (siehe http://msdn.microsoft.com/library/default.asp?url=/library/http/http/namespace_reservations_registrations_and_routing.asp Einzelheiten).|  
|HttpRegistrationAlreadyExists|HTTP kann die angegebene URL nicht registrieren. Diese URL wurde bereits von einer anderen Anwendung mit HTTP.SYS registriert.|  
|HttpRegistrationPortInUse|HTTP kann die angegebene URL nicht registrieren, da der angegebene TCP-Anschluss von einer anderen Anwendung verwendet wird.|  
|HttpSendFailure|Fehler beim Erstellen der HTTP-Anforderung für das angegebene Element. Vergewissern Sie sich, dass es sich nicht um eine fehlende Übereinstimmung bei der Sicherheitsbindung handelt. Überprüfen Sie ferner, dass der Dienst nicht für Secure Sockets Layer konfiguriert ist.|  
|MessageXmlProtocolError|Problem mit dem XML, das vom Netzwerk empfangen wurde. Weitere Informationen finden Sie in der inneren Ausnahme.|  
|MissingContentType|Der Empfänger hat einen Fehler zurückgegeben, der anzeigt, dass der Inhaltstyp in der Anforderung an das angegebene Element fehlte. Weitere Informationen finden Sie in der inneren Ausnahme.|  
|ProxyAuthenticationLevelMismatch|In den Anmeldeinformationen für die HTTP-Proxyauthentifizierung ist eine gegenseitige Authentifizierungsanforderung angegeben, die strenger ist als die Anforderung für die Zielserverauthentifizierung.|  
|ProxyImpersonationLevelMismatch|In den Anmeldeinformationen für die HTTP-Proxyauthentifizierung ist eine Identitätswechseleinschränkung angegeben, die strenger ist als die Einschränkung für die Zielserverauthentifizierung.|  
|SecureChannelFailure|Es konnte kein sicherer Kanal für SSL/TLS mit der angegebenen Stelle eingerichtet werden.|  
|TrustFailure|Es konnte keine Vertrauensstellung für den sicheren SSL/TLS-Kanal mit der angegebenen Stelle eingerichtet werden.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|Eine explizite Proxyadresse kann nicht zusammen mit UseDefaultWebProxy=true im HttpTransportBinding-Element angegeben werden.|
