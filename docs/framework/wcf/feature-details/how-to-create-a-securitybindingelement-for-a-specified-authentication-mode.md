---
title: "Vorgehensweise: Erstellen eines SecurityBindingElement f&#252;r einen angegebenen Authentifizierungsmodus | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# Vorgehensweise: Erstellen eines SecurityBindingElement f&#252;r einen angegebenen Authentifizierungsmodus
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stellt verschiedene Modi bereit, mit denen sich Clients und Dienste gegenseitig authentifizieren.Sie können Sicherheitsbindungselemente für diese Authentifizierungsmodi erstellen. Dazu verwenden Sie statische Methoden für die <xref:System.ServiceModel.Channels.SecurityBindingElement>\-Klasse oder die Konfiguration, wie im folgenden Beispiel dargestellt.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den 18 Authentifizierungsmodi finden Sie unter [SecurityBindingElement\-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
## Beispiel  
 Im folgenden Codebeispiel werden Methoden zum Erstellen von Bindungen für die verschiedenen Authentifizierungsmodi veranschaulicht.  
  
> [!NOTE]
>  Nachdem eine Instanz des <xref:System.ServiceModel.Channels.SecurityBindingElement>\-Objekts erstellt wurde, sind einige Eigenschaften unveränderlich, wie beispielsweise <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> und <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.`set` für diese Eigenschaften aufzurufen, hat keinen Effekt.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## Siehe auch  
 [SecurityBindingElement\-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)   
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)