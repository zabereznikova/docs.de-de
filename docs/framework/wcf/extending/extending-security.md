---
title: Erweitern der Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94aefe80674c5b4ec6fcce6a41d9b68e093f4262
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="extending-security"></a>Erweitern der Sicherheit
Um neue Anspruchstypen und benutzerdefinierte Token aufnehmen zu können, können Sie die Sicherheitsinfrastruktur von Windows Communication Foundation (WCF) erweitern. Die Themen dieses Abschnitts erläutern die entsprechende Vorgehensweise.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Sicherheitsarchitektur](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 Führt Sie durch die Architektur des WCF-Sicherheitssystems.  
  
 [Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 Erklärt die Verwendung des Identitätsmodells bei der Überprüfung von benutzerdefinierten Anmeldeinformationen.  
  
 [ Benutzerdefinierte Token](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 Bei ausgestellten Token aus einem Sicherheitstokendienst handelt es sich in der Regel um SAML-Token. Dieses Thema erklärt das Erstellen eines benutzerdefinierten Tokentyps.  
  
 [Benutzerdefinierte Autorisierung](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 Erklärt das Implementieren einer benutzerdefinierten Autorisierung.  
  
 [Überschreiben der Identität eines Dienstes zur Authentifizierung](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 Beschreibt das Überschreiben der Identität eines Dienstes zur Authentifizierung.  
  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 Veranschaulicht das Überprüfen einer benutzerdefinierten Endpunktidentität.  
  
 [Vorgehensweise: Verwenden von separaten X.509-Zertifikaten für Signieren und Verschlüsselung](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Nachrichten werden in der Regel mit einem einzigen Zertifikat signiert und verschlüsselt. Dieses Thema erklärt, wie Zertifikate bei Bedarf verwendet werden.  
  
 [Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X.509-Zertifikats](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 Erläutert, wie so ändern Sie den Kryptografieanbieter verwendet, um private Schlüssel eines x. 509-Zertifikats bereitzustellen und den Anbieter in der Windows Communication Foundation (WCF)-Framework zu integrieren.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Einfache WCF-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)
