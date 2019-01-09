---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 6cce178910767d7fd197aff0d007b7cc3f4e60f3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151123"
---
# <a name="ltwindowsstreamsecuritygt"></a>&lt;windowsStreamSecurity&gt;
Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<WindowsStreamSecurity >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|protectionLevel|Definiert die Sicherheit auf Nachrichtenebene. Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann. Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit. Folgende Werte sind gültig:<br /><br /> – None: Kein Schutz.<br />-Anmeldung: Nachrichten werden signiert.<br />-"EncryptAndSign" fest: Nachrichten werden signiert und verschlüsselt.<br /><br /> Der Standardwert ist EncryptAndSign.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades. Vor allem WCF bietet Sicherheitsupgrades. Die Konfiguration dieser transportsichersicherheit wird durch dieses Konfigurationselement sowie durch gekapselt [ \<SslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden können  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
