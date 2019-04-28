---
title: <security> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: bac8b9c4af812e924296008fa81227d181b30c0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670429"
---
# <a name="security-of-ws2007httpbinding"></a>\<security> of \<ws2007HttpBinding>
Stellt die Sicherheitseinstellungen der Verwendung der [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) Element.  
  
 \<system.serviceModel>  
\<bindings>  
\<ws2007HttpBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`mode`|-   Optional. Gibt den angewendeten Sicherheitstyp an. Die Standardeinstellung ist `Message`.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>Mode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`None`|Die Sicherheitsfunktionen sind deaktiviert.|  
|`Transport`|Die Sicherheit wird über HTTPS bereitgestellt. Der Dienst muss mit Secure Sockets Layer (SSL)-Zertifikaten konfiguriert werden. Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert. Die Clientauthentifizierung wird durch die `ClientCredentials` Attribut der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) Element.|  
|`Message`|Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt. Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert. In diesem Modus kann eine Reihe von Funktionen festgelegt werden, z.&amp;#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad durch die <xref:System.ServiceModel.Security.SecurityMessageProperty> auf den Nachrichtentext angewendet werden soll. Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
|`TransportWithMessageCredential`|In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher. Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|Definiert die Sicherheitseinstellungen für den Transport. Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ. Diese Einstellungen werden nur übernommen, wenn der Modus auf Transport festgelegt ist.|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|Definiert die Sicherheitseinstellungen für die Nachricht. Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ. Diese Einstellungen werden nicht übernommen, wenn der Modus auf Transport festgelegt ist.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Eine sichere Bindung für HTTP-Transportanwendungen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Element ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-*-Spezifikationen implementieren. Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
