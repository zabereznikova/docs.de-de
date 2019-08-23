---
title: <message>Element von<netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
ms.openlocfilehash: cbbacee00533b72d9e06ee3a79d1e9c0414b337c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931645"
---
# <a name="message-element-of-nettcpbinding"></a>\<Message > Element von \<NetTcpBinding >
Definiert den Typ der Sicherheitsanforderungen auf Nachrichten Ebene für einen Endpunkt, der mit dem [ \<NetTcpBinding->](nettcpbinding.md)konfiguriert ist.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netTcpBinding>  
\<binding>  
\<security>  
\<Message >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<message algorithmSuite="System.Servicemodel.Security.SecurityAlgorithmsuite"
         clientCredentialType="None/Windows/UserName/Certificate/IssuedToken" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`algorithmSuite`|Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest. Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt. Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.<br /><br /> Mögliche Werte werden in der folgenden Tabelle angezeigt. Der Standardwert ist `Basic256`.<br /><br /> Wenn die Dienstbindung einen `algorithmSuite`-Wert angibt, der nicht gleich dem Standardwert ist, und Sie die Konfigurationsdatei mithilfe von „Svcutil.exe“ erstellen, dann wird diese Datei nicht korrekt generiert, und Sie müssen die Konfigurationsdatei manuell bearbeiten, um dieses Attribut auf den gewünschten Wert festzulegen.|  
|`clientCredentialType`|Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit nachrichtenbasierter Sicherheit verwendet werden. Mögliche Werte werden in der folgenden Tabelle angezeigt. Der Standardwert ist `UserName`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|  
  
## <a name="algorithmsuite-attribute"></a>algorithmSuite-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Basic128|Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192|Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256|Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Rsa15|Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Rsa15|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDes|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Rsa15|Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesRsa15|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic128Sha256|Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192Sha256|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Sha256|Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|TripleDesSha256|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Sha256Rsa15|Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Sha256Rsa15|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic256Sha256Rsa15|Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesSha256Rsa15|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|None|Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren. Auf Dienstseite wird dadurch angegeben, dass der Dienst keine Clientanmeldeinformationen erfordert. Auf Clientseite wird dadurch angegeben, dass der Client keine Clientanmeldeinformationen bereitstellt.|  
|Windows|Dies ermöglicht SOAP-Austausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen.|  
|UserName|Ermöglicht es dem Dienst, vom Client zu fordern, sich über eine UserName-Anmeldeinformation zu authentifizieren. WCF unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mithilfe eines Kennworts und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen Anmelde Informationen verwendet werden. Dieser Modus führt entweder zu einem interoperablen Austausch oder zu einer nicht interoperablen Aushandlung basierend auf dem `negotiateServiceCredential`-Attribut.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss. Wenn der Nachrichtensicherheitsmodus verwendet wird und das `negotiateServiceCredential`-Attribut auf `false` festgelegt ist, muss dem Client das Dienstzertifikat zur Verfügung gestellt werden.|  
|IssuedToken|Gibt ein benutzerdefiniertes Token an, das in der Regel von einem Sicherheitstokendienst ausgegeben wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|Definiert die Sicherheitsfunktionen für <xref:System.ServiceModel.Configuration.NetTcpBindingElement>.|  
  
## <a name="remarks"></a>Hinweise  
 Die Nachricht verwendet Sicherheit auf Nachrichtenebene für die Integrität und die Vertraulichkeit der SOAP-Nachricht und für die gegenseitige Authentifizierung der Kommunikationspeers. Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit Nachrichtensicherheits-Bindungselementen konfiguriert, und die SOAP-Nachrichten werden gemäß der WS-Security*-Standards geschützt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.MessageSecurityOverTcp>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
