---
title: "Autorisierung in WCF | Microsoft Docs"
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
  - "Autorisierung [WCF]"
  - "Sicherheit [WCF], Autorisierung"
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Autorisierung in WCF
Autorisierung ist der Prozess, Zugriff und Rechte für Ressourcen zu steuern, z. B. Dienste oder Dateien.Die Themen in diesem Abschnitt zeigen Ihnen die Durchführung dieser grundlegenden Aufgaben in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] auf verschiedene Art und Weise.  
  
## In diesem Abschnitt  
 [Zugriffssteuerungsmechanismen](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 Stellt eine kurze Gliederung der Autorisierungsmechanismen und Verwendungsbeispiele in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereit.  
  
 [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute\-Klasse](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Zeigt den Prozess zum Zugriff auf einen Dienst mit dem <xref:System.Security.Permissions.PrincipalPermissionAttribute> an.  
  
 [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Führt durch die Konfiguration eines Diensts, um die Verwendung der Rollenanbieterfunktion von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] zu aktivieren.  
  
 [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET\-Autorisierungs\-Manager bei einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] kann den Autorisierungs\-Manager zum Verwalten der Autorisierung für eine Website verwenden.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann auf ähnliche Weise die Kombination aus [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\/Autorisierungs\-Manager für die Autorisierung von Clients einsetzen.  
  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 Erläutert die Grundlagen des Verwendens der Identitätsmodellinfrastruktur für auf Ansprüche basierende Autorisierung.  
  
 [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 Erläutert den Unterschied zwischen Delegierung und Identitätswechsel.  
  
## Referenz  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## Verwandte Abschnitte  
 [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)