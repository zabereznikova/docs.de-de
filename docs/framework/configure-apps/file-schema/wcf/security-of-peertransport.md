---
title: '&lt;security&gt; von &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 901a1d0b29fa6ea7d9e520b379dc7c7ff1d1e522
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151955"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;security&gt; von &lt;peerTransport&gt;
Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<PeerTransport >  
\<Sicherheit >  
  
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
|[\<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Definiert einen Peertransport für eine benutzerdefinierte Bindung. Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt. Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<PeerTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Definiert einen Peertransport für eine benutzerdefinierte Bindung.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Transportsicherheit](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Transportprotokolle](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Auswählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
