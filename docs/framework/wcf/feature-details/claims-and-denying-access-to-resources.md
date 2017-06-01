---
title: "Anspr&#252;che und das Verweigern des Zugriffs auf Ressourcen | Microsoft Docs"
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
  - "Ansprüche [WCF], Verweigern des Zugriffs auf Ressourcen"
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Anspr&#252;che und das Verweigern des Zugriffs auf Ressourcen
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützt einen anspruchsbasierten Autorisierungsmechanismus.Systeme erlauben den Zugriff auf Ressourcen basierend auf dem Vorhandensein von Ansprüchen, verweigern jedoch auch häufig einen solchen Zugriff.Derartige Systeme sollten den <xref:System.IdentityModel.Policy.AuthorizationContext> nach Ansprüchen untersuchen, die dazu führen, dass der Zugriff verweigert wird, bevor sie nach Ansprüchen suchen, die zum Zulassen des Zugriffs führen.  
  
 Ein System kann beispielsweise einem Benutzer, der einen Anspruch des Typs `Age`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> und den Ressourcenwert `Under 21` besitzt, den Zugriff auf eine Ressource nur verweigern, wenn dieser außerdem einen Anspruch des Typs `Name`, ein Recht des Typs <xref:System.IdentityModel.Claims.Rights.Identity%2A> und den Ressourcenwert `Mallory` besitzt.Anders ausgedrückt, das System verweigert jedem Benutzer den Zugriff, der unter 21 Jahre alt ist, und lässt den Zugriff zu, wenn der Name Mallory lautet.Um diese semantischen Informationen richtig zu implementieren, ist es wichtig, erst nach dem `Age`\-Anspruch zu suchen und dann zu bestimmen, ob das Alter unter 21 Jahre liegt.Andernfalls kann, wenn Mallory unter 21 ist, der Zugriff auf die Ressource einzig auf Basis des `Name`\-Anspruchs zugelassen werden.  
  
## Siehe auch  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)   
 [Ansprüche und Token](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)