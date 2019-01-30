---
title: <transport> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: b8f84d0ed6c6248e72e3353675c9da96a0678ae6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273305"
---
# <a name="transport-of-ws2007httpbinding"></a>\<Transport > von \<ws2007HttpBinding >
Definiert die Authentifizierungseinstellungen für den HTTP-Transport.  
  
 \<system.serviceModel>  
\<bindings>  
\<ws2007HttpBinding>  
\<binding>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
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
|`realm`|Der Authentifizierungsbereich für die Digest- oder Basisauthentifizierung. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt. Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben. Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu bestimmen, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Die Sicherheitsfunktionen sind deaktiviert.|  
|Standard|Verwendet die Standardauthentifizierung.|  
|Digest|Verwendet Digestauthentifizierung.|  
|Ntlm|Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.|  
|Windows|Verwendet die integrierte Windows-Authentifizierung.|  
|Zertifikat|Verwendet X.509-Zertifikate zum Authentifizieren des Clients.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Die Sicherheitsfunktionen sind deaktiviert.|  
|Standard|Verwendet die Standardauthentifizierung.|  
|Digest|Verwendet Digestauthentifizierung.|  
|Ntlm|Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.|  
|Windows|Verwendet die integrierte Windows-Authentifizierung.|  
|Zertifikat|Verwendet X.509-Zertifikate zum Authentifizieren des Clients.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Gibt die Sicherheitsfunktionen von der [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) Element.|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
