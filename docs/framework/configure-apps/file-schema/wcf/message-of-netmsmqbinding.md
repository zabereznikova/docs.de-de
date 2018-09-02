---
title: '&lt;message&gt; von &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 65a8b0fa120d23931ad218ac67846c066b050af8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402243"
---
# <a name="ltmessagegt-of-ltnetmsmqbindinggt"></a>&lt;message&gt; von &lt;netMsmqBinding&gt;
Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netMsmqBinding>  
\<binding>  
\<Sicherheit >  
\<Meldung >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|algorithmSuite|Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.<br /><br /> Der Standardwert ist `Aes256`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen. Folgende Werte sind gültig:<br /><br /> – None: Dies ermöglicht dem Dienst für die Interaktion mit anonymen Clients. Weder der Dienst noch der Client erfordern Anmeldeinformationen.<br />-Windows: Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen. Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.<br />-UserName: Dies ermöglicht den Dienst die Forderung, die der Client mit benutzernamenanmeldeinformationen authentifiziert werden. In diesem Fall muss die Anmeldeinformationen angegeben werden mithilfe der `clientCredentials` Verhalten **Vorsicht:** Windows Communication Foundation (WCF) unterstützt das Senden eines kennwortdigests oder das Ableiten von Schlüsseln anhand des Kennworts und die Verwendung solcher Schlüssel für nicht nachrichtensicherheit. Aus diesem Grund erzwingt WCF an, dass der Austausch gesichert wird, wenn UserName-Anmeldeinformationen verwendet. Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird. <br /><br /> -Certificate: Dies ermöglicht den Dienst die Forderung, die der Client mit einem Zertifikat authentifiziert. Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden. In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.<br />-CardSpace: Dies ermöglicht den Dienst die Forderung, die der Client mithilfe von CardSpace authentifiziert werden. `serviceCertiifcate` muss im `clientCredential`-Verhalten bereitgestellt werden.<br /><br /> Der Standardwert ist `Windows`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für eine Bindung.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>  
 <xref:System.ServiceModel.MessageSecurityOverMsmq>  
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
