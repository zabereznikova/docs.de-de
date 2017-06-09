---
title: "Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Validierung der Anmeldeinformationen [WCF]"
  - "Anmeldeinformationen [WCF]"
  - "Anmeldeinformationen [WCF], Benutzerdefiniert"
  - "Anmeldeinformationen [WCF], Überprüfung"
  - "Benutzerdefinierte Anmeldeinformationen [WCF]"
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
Die Sicherheit in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] basiert auf dem Austausch von Anmeldeinformationen zwischen Diensten und Clients.  Die meisten Sicherheitsszenarien können durch die Verwendung allgemeiner Anmeldeinformationstypen wie Windows \(Kerberos\), Benutzerrname und Kennwörter sowie Zertifikate erfüllt werden.  Falls jedoch ein neuer Typ von Anmeldeinformationen erforderlich ist, wird in den Themen in diesem Abschnitt die Behandlung und Überprüfung neuer Typen erläutert.  
  
## In diesem Abschnitt  
 [Vorgehensweise: Erstellen eines Dienstes, der ein benutzerdefiniertes Zertifikats\-Validierungssteuerelement verwendet](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Erläutert das Anpassen der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Validierung durch Erben von der <xref:System.IdentityModel.Selectors.X509CertificateValidator>\-Klasse.  
  
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Veranschaulicht, wie die <xref:System.ServiceModel.Description.ClientCredentials>\-Klasse und die <xref:System.ServiceModel.Description.ServiceCredentials>\-Klasse für die Aufnahme neuer Anmeldeinformationstypen erweitert werden.  Dies ist das erste Thema in einer Reihe von Themen, die das Erstellen benutzerdefinierter Anmeldeinformationstypen ermöglichen.  
  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Erläutert das Erstellen eines Sicherheitstokenanbieters zur Behandlung neuer Anmeldeinformationstypen und zum Zurückgeben neuer Token für die Anmeldeinformationen.  Dies ist das zweite Thema in der Reihe.  
  
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Erläutert das Erstellen eines benutzerdefinierten Authentifizierers zum Authentifizieren eines neuen Anmeldeinformationstyps.  Dies ist das dritte Thema in der Reihe.  
  
## Referenz  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## Verwandte Abschnitte  
 [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## Siehe auch  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)