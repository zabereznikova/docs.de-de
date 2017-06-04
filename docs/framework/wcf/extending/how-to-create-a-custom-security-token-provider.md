---
title: "Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters | Microsoft Docs"
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
  - "Sicherheit [WCF], Angeben von Anmeldeinformationen"
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters
In diesem Thema wird beschrieben, wie Sie neue Tokentypen mit einem benutzerdefinierten Sicherheitstokenanbieter erstellen und den Anbieter in einen benutzerdefinierten Sicherheitstoken\-Manager integrieren.  
  
> [!NOTE]
>  Erstellen Sie einen benutzerdefinierten Tokenanbieter, wenn die im <xref:System.IdentityModel.Tokens>\-Namespace gefundenen vom System bereitgestellten Token Ihren Anforderungen nicht entsprechen.  
  
 Der Sicherheitstokenanbieter erstellt eine Sicherheitstokendarstellung basierend auf Daten in den Client\- oder Dienstanmeldeinformationen.  Um den benutzerdefinierten Sicherheitstokenanbieter in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Sicherheit zu verwenden, müssen Sie benutzerdefinierte Anmeldeinformationen und Sicherheitstoken\-Managerimplementierungen erstellen.  
  
 Weitere Informationen über benutzerdefinierte Anmeldeinformationen und Sicherheitstoken\-Manager finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Weitere Informationen über Anmeldeinformationen, Sicherheitstoken\-Manager sowie Anbieter\- und Authentifiziererklassen finden Sie unter [Security Architecture](http://msdn.microsoft.com/de-de/16593476-d36a-408d-808c-ae6fd483e28f).  
  
### So erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter  
  
1.  Definieren Sie eine neue von der <xref:System.IdentityModel.Selectors.SecurityTokenProvider>\-Klasse abgeleitete Klasse.  
  
2.  Implementieren Sie die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>\-Methode.  Die Methode ist für die Erstellung und die Rückgabe einer Instanz des Sicherheitstokens verantwortlich.  Im folgenden Beispiel wird eine Klasse mit der Bezeichnung `MySecurityTokenProvider` erstellt und die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>\-Methode überschrieben, um eine Instanz der <xref:System.IdentityModel.Tokens.X509SecurityToken>\-Klasse zurückzugeben.  Der Klassenkonstruktor erfordert eine neue Instanz der <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>\-Klasse.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### So integrieren Sie einen benutzerdefinierten Sicherheitstokenanbieter in einen benutzerdefinierten Sicherheitstoken\-Manager  
  
1.  Definieren Sie eine neue von der <xref:System.IdentityModel.Selectors.SecurityTokenManager>\-Klasse abgeleitete Klasse.  \(Das nachfolgende Beispiel ist von der <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>\-Klasse abgeleitet, die von der <xref:System.IdentityModel.Selectors.SecurityTokenManager>\-Klasse abgeleitet ist.\)  
  
2.  Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>\-Methode, wenn sie noch nicht überschrieben ist.  
  
     Die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>\-Methode ist für die Rückgabe einer Instanz der <xref:System.IdentityModel.Selectors.SecurityTokenProvider>\-Klasse verantwortlich, entsprechend dem <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>\-Parameter, der an die Methode vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheitsframework übergeben wurde.  Ändern Sie die Methode zur Rückgabe der Implementierung des benutzerdefinierten Sicherheitstokenanbieters \(die mit dem vorherigen Verfahren erstellt wurde\), wenn die Methode mit einem entsprechenden Sicherheitstokenparameter aufgerufen wird.  Weitere Informationen zum Sicherheitstoken\-Manager finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
3.  Fügen Sie benutzerdefinierte Logik zur Methode hinzu, um diese zu befähigen, den benutzerdefinierten Sicherheitstokenanbieter basierend auf dem <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>\-Parameter zurückzugeben.  Im folgenden Beispiel wird der benutzerdefinierte Sicherheitstokenanbieter zurückgegeben, wenn die Tokenanforderungen erfüllt werden.  Die Anforderungen umfassen ein  X.509\-Sicherheitstoken und die Nachrichtenrichtung \(die das Token für die Nachrichtenausgabe verwendet\).  In allen anderen Fällen ruft der Code die Basisklasse ab, um das vom System bereitgestellte Verhalten für andere Sicherheitstokenanforderungen zu verwalten.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## Beispiel  
 Im Folgenden wird eine vollständige <xref:System.IdentityModel.Selectors.SecurityTokenProvider>\-Implementierung zusammen mit einer entsprechenden <xref:System.IdentityModel.Selectors.SecurityTokenManager>\-Implementierung gezeigt.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## Siehe auch  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>   
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>   
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>   
 <xref:System.IdentityModel.Tokens.X509SecurityToken>   
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)   
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)   
 [Security Architecture](http://msdn.microsoft.com/de-de/16593476-d36a-408d-808c-ae6fd483e28f)