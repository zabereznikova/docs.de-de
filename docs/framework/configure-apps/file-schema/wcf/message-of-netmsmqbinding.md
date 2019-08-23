---
title: <message> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: b163dcb08e9656e3bde9c7fbb71fa1c92c9957ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931516"
---
# <a name="message-of-netmsmqbinding"></a>\<Message > von \<NetMsmqBinding >

Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a>Syntax

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|algorithmSuite|Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.<br /><br /> Der Standardwert ist `Aes256`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|
|clientCredentialType|Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen. Folgende Werte sind gültig:<br /><br /> Gar Dies ermöglicht dem Dienst, mit anonymen Clients zu interagieren. Weder der Dienst noch der Client erfordern Anmeldeinformationen.<br />Windows Dadurch kann der SOAP-Austausch im authentifizierten Kontext von Windows-Anmelde Informationen erfolgen. Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.<br />User Dadurch kann der Dienst verlangen, dass der Client mit Benutzernamen Anmelde Informationen authentifiziert werden muss. Die Anmelde Informationen müssen in diesem Fall mit dem `clientCredentials` folgenden Verhalten angegeben werden **:**  Windows Communication Foundation (WCF) unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mithilfe eines Kennworts und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit. Daher erzwingt WCF, dass der Exchange-Schutz bei Verwendung von Benutzernamen-Anmelde Informationen geschützt ist. Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird. <br /><br /> Stellt Dadurch kann der Dienst verlangen, dass der Client mit einem Zertifikat authentifiziert werden muss. Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden. In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.<br />CardSpace Dadurch kann der Dienst verlangen, dass der Client mithilfe eines CardSpace authentifiziert werden muss. `serviceCertificate` muss im `clientCredential`-Verhalten bereitgestellt werden.<br /><br /> Der Standardwert ist `Windows`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.|

### <a name="child-elements"></a>Untergeordnete Elemente

None

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für eine Bindung.|

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
