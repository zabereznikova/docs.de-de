---
title: <add> von <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920116"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<> von \<issuerchannelverhaltensweisen hinzufügen >

Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.

> [!NOTE]
> Wenn ein Endpunkt Verhalten ein [ \<Clientanmelde->](clientcredentials.md) Element enthält, wird eine Ausnahme ausgelöst.

\<system.ServiceModel>\
\<Verhalten > \
Verhalten des endpointBehavior-Abschnitts \<> \
\<clientCredentials>\
\<issuedToken>\
\<issuerchannelverhaltensweisen > Element \
\<add>

## <a name="syntax"></a>Syntax

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|issuerAddress|Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.|
|behaviorConfiguration|Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|Enthält eine Auflistung von Windows Communication Foundation (WCF)-Client Endpunkt Verhalten, die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.|

## <a name="remarks"></a>Hinweise

`issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte. `behaviorConfiguration`verweist auf ein Endpunkt Verhalten, das die Anwendung in den von Windows Communication Foundation (WCF) erstellten Kanälen verwendet, um die ausgestellten Token aus den Sicherheitstokendiensten zu erhalten.

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
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
