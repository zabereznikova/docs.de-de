---
title: '&lt;security&gt; von &lt;netTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
author: BrucePerlerMS
ms.openlocfilehash: 045fb60f6ae0fb54dce7fd9bc8c634caee5fddcd
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170690"
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a>&lt;security&gt; von &lt;netTcpBinding&gt;
Definiert die Sicherheitseinstellungen für eine Bindung.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netTcpBinding>  
\<binding>  
\<Sicherheit >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Modus|Dies ist optional. Gibt den angewendeten Sicherheitstyp an. Gültige Werte werden unten gezeigt. Der Standardwert ist `Transport`.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>mode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Die Sicherheitsfunktionen sind deaktiviert.|  
|Transport|Die Transportsicherheit wird durch TLS über TCP oder SPNego gewährleistet. Der Dienst muss unter Umständen mit SSL-Zertifikaten konfiguriert werden. Es ist möglich, den Schutzgrad mit diesem Modus zu steuern.|  
|Meldung|Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt. Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert. Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad auf den Nachrichtentext angewendet werden soll. Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
|TransportWithMessageCredential|Die Transportsicherheit wird mit der Nachrichtensicherheit gekoppelt. Die Transportsicherheit wird durch TLS über TCP oder SPNego bereitgestellt und stellt Integrität, Vertraulichkeit und Serverauthentifizierung sicher. Die Clientauthentifizierung wird durch die SOAP-Nachrichtensicherheit gewährleistet. Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|Definiert die Sicherheitseinstellungen für den Transport. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|Definiert die Sicherheitseinstellungen für die Nachricht. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Bindung|Das Bindungselement, das von der [ \<NetTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## <a name="remarks"></a>Hinweise  
 Alle Standardbindungen stellen Parameter zur Steuerung der Sicherheitsanforderungen für Übertragungen bereit. Diese Parameter beinhalten normalerweise den Sicherheitsmodus, mit dem angegeben wurde, ob Sicherheit auf Nachrichtenebene oder auf Übertragungsebene verwendet wird und welcher Clientanmeldeinformationstyp ausgewählt wurde. Basierend auf der mit diesen Parametern bereitgestellten Optionsauswahl wird ein Kanalstapel mit der entsprechenden Sicherheit erstellt.  
  
 Die von Windows Communication Foundation (WCF) gelieferten und vom System bereitgestellten Bindungen wurden für einige der gängigsten Szenarioanforderungen entwickelt. Diese Bindungen ermöglichen alle die Angabe von Sicherheitsanforderungen für einige bestimmte Zielszenarien.  
  
 Dieses Konfigurationselement stellt die Sicherheitsspezifikationen für `netTcpBinding` bereit. Daraus ergibt sich eine sichere, zuverlässige und optimierte Bindung, die computerübergreifende Kommunikation unterstützt. Diese Bindung generiert standardmäßig einen Laufzeitkommunikationsstapel mit TCP für die Nachrichtenübertragung, Windows-Sicherheit für Nachrichtensicherheit und Authentifizierung, WS-Reliable-Messaging für Zuverlässigkeit sowie binäre Nachrichtencodierung.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
