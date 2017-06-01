---
title: "Erstellen von Anspr&#252;chen und Ressourcenwerte | Microsoft Docs"
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
  - "Ansprüche [WCF], Erstellen und Ressourcenwerte"
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Erstellen von Anspr&#252;chen und Ressourcenwerte
Die <xref:System.IdentityModel.Claims.Claim>\-Klasse bietet mehrere Methoden zum Erstellen von Instanzen von integrierten Anspruchstypen.Von diesen Methoden führen die folgenden keine semantische Prüfung oder Formatüberprüfung für die angegebene Ressource aus:  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> \(überprüft die Länge oder den Inhalt des Bytearrays nicht\)  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> \(überprüft die Länge oder den Inhalt des Bytearrays nicht\)  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 Gehen Sie beim Aufrufen der oben beschriebenen Methoden äußerst sorgfältig vor, um sicherzustellen, dass die übergebenen Ressourcenwerte das richtige Format aufweisen oder die richtigen Informationen enthalten \(oder beides\).  
  
 Die folgenden Methoden werden mit bestimmten Typen verwendet:  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## Siehe auch  
 <xref:System.IdentityModel.Claims.Claim>   
 <xref:System.IdentityModel.Claims.ClaimSet>   
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)