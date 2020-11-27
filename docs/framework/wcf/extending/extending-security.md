---
title: Erweitern der Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: d91f4812dbccb7807be2e0780cccd1d0c38b1f40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273060"
---
# <a name="extending-security"></a>Erweitern der Sicherheit

Wenn Sie neue Anspruchs Typen und benutzerdefinierte Token aufnehmen möchten, können Sie die Sicherheitsinfrastruktur von Windows Communication Foundation (WCF) erweitern. Die Themen dieses Abschnitts erläutern die entsprechende Vorgehensweise.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
 [Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen](custom-credential-and-credential-validation.md)  
 Erklärt die Verwendung des Identitätsmodells bei der Überprüfung von benutzerdefinierten Anmeldeinformationen.  
  
 [Benutzerdefinierte Token](custom-tokens.md)  
 Bei ausgestellten Token aus einem Sicherheitstokendienst handelt es sich in der Regel um SAML-Token. Dieses Thema erklärt das Erstellen eines benutzerdefinierten Tokentyps.  
  
 [Benutzerdefinierte Autorisierung](custom-authorization.md)  
 Erklärt das Implementieren einer benutzerdefinierten Autorisierung.  
  
 [Überschreiben der Identität eines Dienstes zur Authentifizierung](overriding-the-identity-of-a-service-for-authentication.md)  
 Beschreibt das Überschreiben der Identität eines Dienstes zur Authentifizierung.  
  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung](how-to-create-a-custom-client-identity-verifier.md)  
 Veranschaulicht das Überprüfen einer benutzerdefinierten Endpunktidentität.  
  
 [Vorgehensweise: Verwenden von separaten X.509-Zertifikaten zum Signieren und Verschlüsseln](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Nachrichten werden in der Regel mit einem einzigen Zertifikat signiert und verschlüsselt. Dieses Thema erklärt, wie Zertifikate bei Bedarf verwendet werden.  
  
 [Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X.509-Zertifikats](change-cryptographic-provider-x509-certificate-private-key.md)  
 Erläutert, wie der Kryptografieanbieter geändert wird, mit dem der private Schlüssel eines X. 509-Zertifikats bereitgestellt wird, und wie der Anbieter in das Windows Communication Foundation-Framework (WCF) integriert wird.  
  
## <a name="reference"></a>Referenz  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Security](../feature-details/security.md)  
  
 [Einfache WCF-Programmierung](../basic-wcf-programming.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](../feature-details/security-overview.md)
