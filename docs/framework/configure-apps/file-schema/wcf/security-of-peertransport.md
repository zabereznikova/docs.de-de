---
title: <security> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 1aff79bf5867a3a1ebe05e3f812475dac4b413e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670494"
---
# <a name="security-of-peertransport"></a>\<Security > von \<PeerTransport >
Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<peerTransport>  
\<security>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`mode`|Gibt den Typ der anzuwendenden Sicherheit an. Der Standardwert ist Nachricht. Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>mode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`None`|Die Sicherheitsfunktionen sind deaktiviert.|  
|`Transport`|Die Sicherheit wird über HTTPS bereitgestellt.|  
|`Message`|Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.|  
|`TransportWithMessageCredential`|HTTPS stellt Authentifizierung und Vertraulichkeit bereit. Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Definiert einen Peertransport für eine benutzerdefinierte Bindung. Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt. Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<peerTransport>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Definiert einen Peertransport für eine benutzerdefinierte Bindung.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Transportprotokolle](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Auswählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
