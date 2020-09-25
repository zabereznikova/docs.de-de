---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 63368355027856118546bc70183b41864eddb0e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172878"
---
# \<serviceCredentials>

Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`type`|Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|Gibt das zu verwendende Clientzertifikat an, wenn das Clientzertifikat out-of-band verfügbar ist. Dieses Element gibt auch Clientzertifikats-Validierungseinstellungen an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|Gibt das aktuell ausgegebene Token für diesen Dienst an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.|  
|[\<peer>](peer-of-servicecredentials.md)|Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|Gibt die aktuellen Anmeldeinformationen für eine sichere Unterhaltung an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|Gibt ein Zertifikat an, das ein Dienst für die eigene Identifizierung verwendet. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.|  
|[\<userNameAuthentication>](usernameauthentication.md)|Gibt die Einstellungen für Benutzernamen- und Kennwortvalidierung an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.UserNameServiceElement>.|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|Gibt die Einstellungen für die Überprüfung der Windows-Anmeldeinformationen an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsServiceElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
