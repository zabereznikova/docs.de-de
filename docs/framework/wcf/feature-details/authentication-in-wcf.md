---
title: "Authentifizierung in WCF | Microsoft Docs"
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
  - "Authentifizierung [WCF]"
  - "Sicherheit [WCF], Authentifizierung"
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Authentifizierung in WCF
Die folgenden Themen beschreiben eine Anzahl unterschiedlicher Mechanismen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], die eine Authentifizierung ermöglichen, z. B. die Windows\-Authentifizierung, X.509\-Zertifikate sowie Benutzername und Kennwörter.  
  
## In diesem Abschnitt  
 [Gewusst wie: Verwenden des ASP.NET\-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Zu den ASP.NET\-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen\/Kennwort\-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung.In diesem Thema wird erläutert, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste die gleiche Datenbank verwenden können, um Benutzer zu authentifizieren und zu autorisieren.  
  
 [Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort\-Validierungssteuerelements](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen\- und Kennwort\-Validierungssteuerelement integriert wird.  
  
 [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 Als zusätzliche Schutzvorrichtung, kann ein Client den Dienst durch die Angabe der erwarteten *Identität* des Dienstes authentifizieren.Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.  
  
 [Sicherheitsaushandlung und Timeouts](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>\-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>\-Klasse.  
  
 [Debuggen von Windows\-Authentifizierungsfehlern](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows\-Authentifizierung auftreten.  
  
## Referenz  
 <xref:System.ServiceModel>  
  
## Verwandte Abschnitte  
 [Häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)