---
title: <security> von <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: aa01e906ddd2f15007c72bfc2a45122cfb15ba2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736372"
---
# <a name="security-of-nettcpbinding"></a>\<security> von \<netTcpBinding>
Definiert die Sicherheitseinstellungen für eine Bindung.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|Modus|(Optional) Gibt den angewendeten Sicherheitstyp an. Gültige Werte werden unten gezeigt. Der Standardwert ist `Transport`.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.|  
  
## <a name="mode-attribute"></a>mode-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Keine|Die Sicherheitsfunktionen sind deaktiviert.|  
|Transport|Die Transportsicherheit wird durch TLS über TCP oder SPNego gewährleistet. Der Dienst muss unter Umständen mit SSL-Zertifikaten konfiguriert werden. In diesem Modus kann die Schutzstufe gesteuert werden.|  
|`Message`|Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt. Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert. Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmensammlung verwendet werden soll und welcher Schutzgrad auf den Nachrichtentext angewendet werden soll. Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
|TransportWithMessageCredential|Die Transportsicherheit wird mit der Nachrichtensicherheit gekoppelt. Die Transportsicherheit wird durch TLS über TCP oder SPNego bereitgestellt und stellt Integrität, Vertraulichkeit und Serverauthentifizierung sicher. Die Clientauthentifizierung wird durch die SOAP-Nachrichtensicherheit gewährleistet. Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|Definiert die Sicherheitseinstellungen für den Transport. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.|  
|[\<message>](message-element-of-nettcpbinding.md)|Definiert die Sicherheitseinstellungen für die Nachricht. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|binding|Das Bindungs Element von [\<netTcpBinding>](nettcpbinding.md) .|  
  
## <a name="remarks"></a>Bemerkungen  
 Alle Standardbindungen stellen Parameter zur Steuerung der Sicherheitsanforderungen für Übertragungen bereit. Diese Parameter beinhalten normalerweise den Sicherheitsmodus, mit dem angegeben wurde, ob Sicherheit auf Nachrichtenebene oder auf Übertragungsebene verwendet wird und welcher Clientanmeldeinformationstyp ausgewählt wurde. Basierend auf der mit diesen Parametern bereitgestellten Optionsauswahl wird ein Kanalstapel mit der entsprechenden Sicherheit erstellt.  
  
 Die von Windows Communication Foundation (WCF) gelieferten und vom System bereitgestellten Bindungen wurden für einige der gängigsten Szenarioanforderungen entwickelt. Diese Bindungen ermöglichen alle die Angabe von Sicherheitsanforderungen für einige bestimmte Zielszenarien.  
  
 Dieses Konfigurationselement stellt die Sicherheitsspezifikationen für `netTcpBinding` bereit. Daraus ergibt sich eine sichere, zuverlässige und optimierte Bindung, die computerübergreifende Kommunikation unterstützt. Diese Bindung generiert standardmäßig einen Laufzeitkommunikationsstapel mit TCP für die Nachrichtenübertragung, Windows-Sicherheit für Nachrichtensicherheit und Authentifizierung, WS-Reliable-Messaging für Zuverlässigkeit sowie binäre Nachrichtencodierung.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
