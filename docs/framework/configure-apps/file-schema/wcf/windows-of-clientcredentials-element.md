---
title: "&lt;windows&gt; des &lt;clientCredentials&gt;-Elements | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;windows&gt; des &lt;clientCredentials&gt;-Elements
Gibt die Einstellungen für Windows\-Anmeldeinformationen an, die zum Darstellen des Clients verwendet werden.  
  
## Syntax  
  
```  
  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`allowedImpersonationLevel`|Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.  Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.  Folgende Werte sind gültig:<br /><br /> -   Identification: Der Server erhält die Identitäts\- und Berechtigungsinformationen des Clients, kann aber den Client nicht imitieren.<br />-   Impersonation: Der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.<br />-   Delegation: Der Serverprozess kann den Sicherheitskontext des Clients in Remotesystemen imitieren.<br />-   Anonymous: Der Server kann den Client nicht imitieren oder identifizieren.<br />-   None: Es ist keine Identitätswechselebene zugeordnet.<br /><br /> Die Standardeinstellung ist Identification.  Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Durch das Festlegen dieser Eigenschaft auf `true` kann die Authentifizierung auf NTLM herabgestuft werden, wenn Kerberos nicht verfügbar ist.<br /><br /> Das Festlegen dieser Eigenschaft auf `false` führt dazu, dass [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] nach dem Best\-Effort\-Prinzip eine Ausnahme auslöst, wenn NTLM verwendet wird.  Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM\-Anmeldeinformationen über die Verbindung gesendet werden.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>   
 <xref:System.ServiceModel.Security.WindowsClientCredential>   
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)   
 [Verwenden von Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)