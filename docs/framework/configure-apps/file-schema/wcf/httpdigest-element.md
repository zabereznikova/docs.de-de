---
title: "&lt;httpDigest&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt;httpDigest&gt;-Element
Gibt Anmeldeinformationen vom Typ Digest an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.  
  
## Syntax  
  
```  
  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`impersonationLevel`|Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.  Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.  Folgende Werte sind gültig:<br /><br /> -   Identification: Der Server erhält die Identitäts\- und Berechtigungsinformationen des Clients, kann aber den Client nicht imitieren.<br />-   Impersonation: Der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.<br />-   Delegation: Der Serverprozess kann den Sicherheitskontext des Clients in Remotesystemen imitieren.<br />-   Anonymous: Der Server kann den Client nicht imitieren oder identifizieren.<br />-   None: Es ist keine Identitätswechselebene zugeordnet.<br /><br /> Die Standardeinstellung ist Identification.  Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## Hinweise  
 Ein Digest ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.  Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.  Der Client kann den Hash berechnen und an den Dienst senden.  Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.  Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.  
  
 Diese Funktion muss mit Active Directory unter Windows und unter IIS \(Internet Information Services\) aktiviert werden.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Digestauthentifizierung in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>   
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>   
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>   
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)