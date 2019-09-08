---
title: Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 1418d4155bc7f2fefc9f3e6caf4d3a264747a667
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795815"
---
# <a name="custom-credential-and-credential-validation"></a>Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
Die Sicherheit in Windows Communication Foundation (WCF) basiert auf dem Austausch von Anmelde Informationen zwischen Diensten und Clients. Die meisten Sicherheitsszenarien können durch die Verwendung allgemeiner Anmeldeinformationstypen wie Windows (Kerberos), Benutzerrname und Kennwörter sowie Zertifikate erfüllt werden. Falls jedoch ein neuer Typ von Anmeldeinformationen erforderlich ist, wird in den Themen in diesem Abschnitt die Behandlung und Überprüfung neuer Typen erläutert.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes zertifikatvalidator verwendet](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Erläutert, wie Sie die WCF-Validierung anpassen, indem <xref:System.IdentityModel.Selectors.X509CertificateValidator> Sie von der-Klasse erben.  
  
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client-und Dienst Anmelde Informationen](walkthrough-creating-custom-client-and-service-credentials.md)  
 Veranschaulicht, wie die <xref:System.ServiceModel.Description.ClientCredentials> Klassen und <xref:System.ServiceModel.Description.ServiceCredentials> erweitert werden, um neue Anmelde Informationstypen zu ermöglichen. Dies ist das erste Thema in einer Reihe von Themen, die das Erstellen benutzerdefinierter Anmeldeinformationstypen ermöglichen.  
  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md)  
 Erläutert das Erstellen eines Sicherheitstokenanbieters zur Behandlung neuer Anmeldeinformationstypen und zum Zurückgeben neuer Token für die Anmeldeinformationen. Dies ist das zweite Thema in der Reihe.  
  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](how-to-create-a-custom-security-token-authenticator.md)  
 Erläutert das Erstellen eines benutzerdefinierten Authentifizierers zum Authentifizieren eines neuen Anmeldeinformationstyps. Dies ist das dritte Thema in der Reihe.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Authentifizierung](../feature-details/authentication-in-wcf.md)  
  
 [Verbund und ausgestellte Token](../feature-details/federation-and-issued-tokens.md)  
  
 [Autorisierung](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheit](../feature-details/security.md)
