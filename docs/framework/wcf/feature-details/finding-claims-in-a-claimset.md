---
title: "Suchen von Anspr&#252;chen in einem ClaimSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ansprüche [WCF]"
  - "Ansprüche [WCF], Suchen in einem ClaimSet"
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Suchen von Anspr&#252;chen in einem ClaimSet
Bei der Verwendung der anspruchbasierten Autorisierung muss häufig der Inhalt eines <xref:System.IdentityModel.Claims.ClaimSet> für bestimmte Anspruchstypen überprüft werden.Verwenden Sie die <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>\-Methode, um <xref:System.IdentityModel.Claims.ClaimSet> auf das Vorhandensein eines bestimmten Anspruchs zu überprüfen.Diese Methode ist leistungsstärker als eine direkte Iteration über <xref:System.IdentityModel.Claims.ClaimSet>.Im folgenden Beispiel wird diese Verwendung veranschaulicht.Beachten Sie, dass die Parameter `claimType` und `claimRight``null` sein können.In diesem Fall entsprechen die Parameter allen Anspruchstypen und Anspruchsrechten.  
  
## Beispiel  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## Siehe auch  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)