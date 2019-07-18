---
title: <security> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: fa31dda3274c9768694bdf5232f31554899e1d82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670520"
---
# <a name="security-of-netnamedpipebinding"></a>\<security> of \<netNamedPipeBinding>
Definiert die Sicherheitseinstellungen für eine Bindung.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netNamedPipeBinding>  
\<binding>  
\<security>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Modus|Gibt den Sicherheitstyp an, der auf diese Bindung angewendet wird. Folgende Werte sind gültig:<br /><br /> – None: Dadurch werden die Sicherheitsfunktionen deaktiviert.<br />-Transport: Sicherheit wird bereitgestellt, mit der zugrunde liegende transportsicherheit gewährleistet. Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.<br />– Der Standardwert ist Transport. Dieses Attribut ist vom Typ <xref:System.ServiceModel.NetNamedPipeSecurityMode>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|transport|Definiert die Sicherheitseinstellungen für den Transport. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Bindung|Das Bindungselement, das von der [ \<NetNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Ausählen eines Anmeldeinformationentyps](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
