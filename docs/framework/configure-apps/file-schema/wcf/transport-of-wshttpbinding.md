---
title: <transport> von <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 384267e3d018d714f95356461eb303bc9ec0cb3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934639"
---
# <a name="transport-of-wshttpbinding"></a>\<Transport > von \<WSHttpBinding >

Definiert die Authentifizierungseinstellungen für den HTTP-Transport.

\<System. Service Model > \
\<Bindungen > \
\<wsHttpBinding>\
\<Bindungs > \
\<Sicherheits > \
\<transport>

## <a name="syntax"></a>Syntax

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a>Typ

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`clientCredentialType`|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.|
|`proxyCredentialType`|Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.|
|`realm`|Eine Zeichenfolge, die den Authentifizierungsbereich für die Hashwert- oder Standardauthentifizierung angibt. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt. Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben. Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.|
|`policyEnforcement`|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.<br />3.  Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|

## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`None`|Die Sicherheitsfunktionen sind deaktiviert.|
|`Basic`|Verwendet die Standardauthentifizierung.|
|`Digest`|Verwendet Digestauthentifizierung.|
|`Ntlm`|Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.|
|`Windows`|Verwendet die integrierte Windows-Authentifizierung.|
|`Certificate`|Verwendet X.509-Zertifikate zum Authentifizieren des Clients.|

## <a name="proxycredentialtype-attribute"></a>proxyCredentialType-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`None`|Die Sicherheitsfunktionen sind deaktiviert.|
|`Basic`|Verwendet die Standardauthentifizierung.|
|`Digest`|Verwendet Digestauthentifizierung.|
|`Ntlm`|Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.|
|`Windows`|Verwendet die integrierte Windows-Authentifizierung.|
|`Certificate`|Verwendet X.509-Zertifikate zum Authentifizieren des Clients.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|Stellt die Sicherheitsfunktionen des [ \<WSHttpBinding->](wshttpbinding.md)dar.|

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
