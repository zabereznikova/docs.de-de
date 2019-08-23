---
title: <security> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936587"
---
# <a name="security-of-webhttpbinding"></a>\<Sicherheits > von \<WebHttpBinding >
Gibt die Sicherheitsanforderungen für einen Endpunkt an, der mit einem [ \<WebHttpBinding->](webhttpbinding.md)konfiguriert wurde.  
  
 \<system.ServiceModel>  
\<bindings>  
\<webHttpBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Modus|Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird. Die Standardeinstellung ist `None`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Mode-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|None|Die Sicherheitsfunktionen sind deaktiviert.|  
|Transport|Die Sicherheit wird über HTTPS bereitgestellt. Der Dienst muss mit SSL-Zertifikaten konfiguriert werden. Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert. Die Client Authentifizierung wird über das `ClientCredentialType` -Attribut [ \<des Transport >](transport-of-webhttpbinding.md)gesteuert.|  
|TransportCredentialOnly|Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit. Er bietet dagegen HTTP-basierte Clientauthentifizierung. Dieser Modus sollte mit Vorsicht angewendet werden. Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|Definiert die Sicherheitseinstellungen für den Transport. Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|Ein Bindungs Element, das verwendet wird, um Endpunkte für Windows Communication Foundation (WCF)-Webdienste zu konfigurieren, die auf HTTP-Anforderungen anstelle von SOAP-Nachrichten reagieren.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Ausählen eines Anmeldeinformationentyps](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
- [WCF-Web-HTTP-Programmiermodell](../../../wcf/feature-details/wcf-web-http-programming-model.md)
