---
title: Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3ca7726f3a6a0c5faaab1cbbd0b31125ce0c1d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="custom-credential-and-credential-validation"></a>Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
Die Sicherheit in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] basiert auf dem Austausch von Anmeldeinformationen zwischen Diensten und Clients. Die meisten Sicherheitsszenarien können durch die Verwendung allgemeiner Anmeldeinformationstypen wie Windows (Kerberos), Benutzerrname und Kennwörter sowie Zertifikate erfüllt werden. Falls jedoch ein neuer Typ von Anmeldeinformationen erforderlich ist, wird in den Themen in diesem Abschnitt die Behandlung und Überprüfung neuer Typen erläutert.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: erstellen ein Diensts, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Erläutert das Anpassen der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Validierung durch Erben von der <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse.  
  
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Veranschaulicht das Erweitern der <xref:System.ServiceModel.Description.ClientCredentials> und <xref:System.ServiceModel.Description.ServiceCredentials> Klassen für die Aufnahme neuer Anmeldeinformationstypen. Dies ist das erste Thema in einer Reihe von Themen, die das Erstellen benutzerdefinierter Anmeldeinformationstypen ermöglichen.  
  
 [Vorgehensweise: Erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Erläutert das Erstellen eines Sicherheitstokenanbieters zur Behandlung neuer Anmeldeinformationstypen und zum Zurückgeben neuer Token für die Anmeldeinformationen. Dies ist das zweite Thema in der Reihe.  
  
 [Vorgehensweise: erstellen ein benutzerdefinierten Sicherheitstokenauthentifizierers](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Erläutert das Erstellen eines benutzerdefinierten Authentifizierers zum Authentifizieren eines neuen Anmeldeinformationstyps. Dies ist das dritte Thema in der Reihe.  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)
