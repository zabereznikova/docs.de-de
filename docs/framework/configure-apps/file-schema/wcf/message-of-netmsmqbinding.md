---
title: "&lt;message&gt; von &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;message&gt; von &lt;netMsmqBinding&gt;
Definiert die SOAP\-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`\-Bindung.  
  
## Syntax  
  
```  
  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|algorithmSuite|Legt die Nachrichtenverschlüsselungs\- und Key Wrap\-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ\-Transport gesendete Nachrichten sicherstellen.<br /><br /> Der Standardwert ist `Aes256`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ\-Transport gesendete Nachrichten verwendet werden sollen.  Folgende Werte sind gültig:<br /><br /> -   None: Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren.  Weder der Dienst noch der Client erfordern Anmeldeinformationen.<br />-   Windows: Dies ermöglicht den SOAP\-Austauschvorgängen, sich unter dem authentifizierten Kontext von Windows\-Anmeldeinformationen zu befinden.  Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.<br />-   UserName: Dies aktiviert den Dienst, der erfordert, dass der Client mithilfe von UserName\-Anmeldeinformationen authentifiziert wird.  Die Anmeldeinformationen müssen in diesem Fall über das `clientCredentials`\-Verhalten angegeben werden. **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] unterstützt kein Kennwortdigest und keine ableitenden Schlüssel mit Kennwörtern sowie keine Verwendung solcher Schlüssel für die Nachrichtensicherheit.  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] setzt daher prinzipiell durch, dass der Austausch gesichert wird, wenn UserName\-Anmeldeinformationen verwendet werden.  Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`\-Verhaltens und `serviceCertificate` angegeben wird. <br /><br /> -   Certificate: Dies ermöglicht dem Dienst, die Clientauthentifizierung mithilfe eines Zertifikats zu anzufordern.  Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`\-Verhalten angegeben werden.  In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`\-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.<br />-   CardSpace: Dies ermöglicht es dem Dienst zu verlangen, dass der Client mithilfe von CardSpace authentifiziert wird.  `serviceCertiifcate` muss im `clientCredential`\-Verhalten bereitgestellt werden.<br /><br /> Der Standardwert ist `Windows`.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für eine Bindung.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>   
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>   
 <xref:System.ServiceModel.MessageSecurityOverMsmq>   
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)