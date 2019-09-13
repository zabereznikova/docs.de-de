---
title: <issuerChannelBehaviors>-Element
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893157"
---
# <a name="issuerchannelbehaviors-element"></a>\<issuerchannelverhaltens>-Element

Enthält eine Auflistung von Windows Communication Foundation (WCF)-clientend Punkt Verhaltensweisen (in der Konfiguration definiert), die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen. Das definierte Verhalten kann keine [ \<Clientanmelde->](clientcredentials.md) Elemente enthalten.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<System. Service Model->](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<Verhaltens >](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointverhaltens->](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<Verhaltens >](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<Client Anmelde Informationen >](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<IssuedToken->](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerchannelverhaltens>

## <a name="syntax"></a>Syntax

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|Fügt der Auflistung ein Verhalten hinzu.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.|

## <a name="remarks"></a>Hinweise

Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss. Beispielsweise, wenn ein [ \<DataContractSerializer->](datacontractserializer-element.md) Behavior-Element eingeschlossen werden muss.

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Dienstidentität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Verbund und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Sichern von Clients](../../../wcf/securing-clients.md)
- [Vorgehensweise: Erstellen eines Verbund Clients](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Verbund und ausgestellte Token](../../../wcf/feature-details/federation-and-issued-tokens.md)
