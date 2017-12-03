---
title: "Kernkommunikation: HTTP-HTTPS-Transportkanäle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81eb778d70722cb44fa8dd4bc3f1152a12d87199
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-httphttps-transport-channels"></a>Kernkommunikation: HTTP/HTTPS-Transportkanäle
Dieses Thema enthält alle Ausnahmen, die von HTTP/HTTPS-Transportkanälen von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|Die angegebene Identitätswechselebene wurde angegeben. Die HTTP-Digestauthentifizierung kann Identitätswechselebenen jedoch nur in Kombination mit expliziten Anmeldeinformationen unterstützen.|  
|FramingContentTypeMismatch|Der angegebene Inhaltstyp wurde vom angegebenen Dienst nicht unterstützt. Möglicherweise besteht keine Übereinstimmung zwischen Client- und Dienstbindung.|  
|Hosting_SslSettingsMisconfigured|Die Secure Sockets Layer-Einstellungen für den angegebenen Dienst stimmen nicht mit den Einstellungen der Internet Information Services überein.|  
|HttpAuthSchemeAndClientCert|Die Konfiguration der HTTPS-Listenerfactory erfordert ein Clientzertifikat und das angegebene Authentifizierungsschema. Es kann jedoch immer nur jeweils eine Form der Clientauthentifizierung erforderlich sein.|  
|HttpReceiveFailure|Fehler beim Empfangen der HTTP-Antwort für das angegebene Element. Möglicherweise verwendet die Dienstendpunktbindung kein HTTP-Protokoll. Eine andere mögliche Ursache ist, dass der HTTP-Anforderungskontext vom Server abgebrochen wird (vermutlich auf das Herunterfahren eines Diensts zurückzuführen). Weitere Informationen finden Sie in den Serverprotokollen.|  
|HttpRegistrationAccessDenied|HTTP kann die angegebene URL nicht registrieren. Der Prozess hat keine Zugriffsrechte für diesen Namespace (weitere Informationen finden Sie unter http://msdn.microsoft.com/library/default.asp?url=/library/http/http/namespace_reservations_registrations_and_routing.asp).|  
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
