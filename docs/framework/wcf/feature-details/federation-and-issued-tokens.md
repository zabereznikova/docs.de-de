---
title: Verbund und ausgestellte Token
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: dffba51c1bf1aaffbed8725aafc96fd747cb31c6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559251"
---
# <a name="federation-and-issued-tokens"></a>Verbund und ausgestellte Token
Mit Windows Communication Foundation (WCF) können Sie Clients erstellen, die sicher mit Diensten kommunizieren, die die WS-Verbund-und WS-Trust-Spezifikationen implementieren. Die Spezifikationen verwenden XML, SOAP und Web Services Description Language (WSDL), um Mechanismen zu bieten, die Authentifizierung und Autorisierung über verschiedene Vertrauensbereiche hinweg zu ermöglichen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verbund](federation.md)  
 Bietet einen Überblick über den Verbund.  
  
 [Verbund und Vertrauenswürdigkeit](federation-and-trust.md)  
 Führt die Entwurfsprobleme auf, die beim Erstellen von Verbunddiensten oder -clients berücksichtigt werden müssen.  
  
 [Vorgehensweise: Erstellen eines Verbundclients](how-to-create-a-federated-client.md)  
 Beschreibt die Grundlagen der Erstellung eines Verbund Clients mit WCF.  
  
 [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](how-to-configure-credentials-on-a-federation-service.md)  
 Beschreibt die Schritte beim Erstellen eines Verbunddiensts.  
  
 [Vorgehensweise: Erstellen einer WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)  
 Beschreibt, wie man Clients und Dienste konfiguriert, die `WSFederationHttpBinding` verwenden.  
  
 [Vorgehensweise: Erstellen eines Sicherheitstokendiensts](how-to-create-a-security-token-service.md)  
 Beschreibt die Schritte beim Erstellen eines Sicherheitstokendiensts.  
  
 [SAML-Token (Security Assertions Markup Language) und Ansprüche](saml-tokens-and-claims.md)  
 Beschreibt Security Assertions Markup Language (SAML)-Token, die erweiterbar sind und es ermöglichen, Rich Claim-Typen zu erstellen.  
  
 [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](how-to-configure-a-local-issuer.md)  
 Beschreibt, wie ein lokaler Aussteller von Sicherheitstoken erstellt wird.  
  
 [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Beschreibt, wie Sicherheitssitzungen auf `WSFederationHttpBinding` deaktiviert werden. Sichere Sitzungen müssen deaktiviert werden, wenn eine Webfarm erstellt wird, die eine Sitzung für jeden Client erfordert.  
  
## <a name="reference"></a>Referenz  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a>Siehe auch

- [Autorisierung](authorization-in-wcf.md)
- [Benutzerdefinierte Token](../extending/custom-tokens.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
