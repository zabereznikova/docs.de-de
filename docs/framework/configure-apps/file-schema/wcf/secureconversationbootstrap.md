---
title: <secureConversationBootstrap>
ms.date: 03/30/2017
ms.assetid: 66b46f95-fa2d-4b5b-b6ce-0572ab0cdd50
ms.openlocfilehash: e39458e7e0bac15429ad3d34c4fbba0f55d254f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166990"
---
# <a name="secureconversationbootstrap"></a>\<secureConversationBootstrap>
Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<security>  
\<secureConversationBootstrap>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<secureConversationBootstrap allowSerializedSigningTokenOnReply="Boolean"
                             authenticationMode="AuthenticationMode"
                             defaultAlgorithmSuite="SecurityAlgorithmSuite"
                             includeTimestamp="Boolean"
                             requireDerivedKeys="Boolean"
                             keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
                             messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
                             messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"
                             requireDerivedKeys="Boolean"
                             requireSecurityContextCancellation="Boolean"
                             requireSignatureConfirmation="Boolean"
                             securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
                             includeTimestamp="Boolean" />
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`allowSerializedSigningTokenOnReply`|Dies ist optional. Ein boolescher Wert, der angibt, ob ein serialisiertes Token für eine Antwort verwendet werden kann. Der Standardwert ist `false`. Beim Verwenden einer Dualbindung ist `true` die Standardeinstellung, vorgenommene Einstellungen werden ignoriert.|  
|`authenticationMode`|Gibt den SOAP-Authentifizierungsmodus an, der zwischen Initiator und Beantworter verwendet wird.<br /><br /> Der Standardwert ist sspiNegotiated.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Configuration.AuthenticationMode>.|  
|`defaultAlgorithmSuite`|Die Sicherheitsalgorithmussammlung definiert verschiedene Algorithmen, wie zum Beispiel Kanonisierung, Digest, KeyWrap, Signatur, Verschlüsselung und KeyDerivation. Jede Sicherheitsalgorithmussammlung definiert Werte für diese verschiedenen Parameter. Die nachrichtenbasierte Sicherheit wird über diese Algorithmen sichergestellt.<br /><br /> Dieses Attribut wird verwendet, wenn mit einer anderen Plattform gearbeitet wird, die eine Reihe von Nicht-Standardalgorithmen verwendet. Sie sollten die Stärken und Schwächen der relevanten Algorithmen kennen, wenn Sie Änderungen an dieser Einstellung vornehmen. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Die Standardeinstellung ist `Basic256`.|  
|`includeTimestamp`|Ein boolescher Wert, der angibt, ob jede Nachricht einen Zeitstempel enthält. Die Standardeinstellung ist `true`.|  
|`keyEntropyMode`|Gibt an, wie Schlüssel für das Sichern von Nachrichten berechnet werden. Schlüssel können nur auf dem Schlüsselmaterial des Clients, des Diensts oder auf einer Kombination von beiden basiert werden. Gültige Werte sind:<br /><br /> -   ClientEntropy: Der Sitzungsschlüssel basiert vom Client bereitgestellten Schlüsselmaterial.<br />-ServerEntropy: Der Sitzungsschlüssel basiert vom Dienst bereitgestellten Schlüsselmaterial.<br />-CombinedEntropy: Der Sitzungsschlüssel basiert auf dem Client und Dienst bereitgestellten Schlüsselmaterial.<br /><br /> Der Standardwert ist CombinedEntropy.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`messageProtectionOrder`|Legt die Reihenfolge fest, in der Sicherheitsalgorithmen der Nachrichtenebene auf die Nachricht angewendet werden. Folgende Werte sind gültig:<br /><br /> -SignBeforeEncrypt: Melden Sie sich zuerst, dann verschlüsseln.<br />-   SignBeforeEncryptAndEncryptSignature: Signieren, verschlüsseln und Signatur verschlüsseln.<br />-EncryptBeforeSign: Zuerst, dann verschlüsseln Sie anmelden.<br /><br /> Beim Verwenden von gegenseitigen Zertifikaten mit WS-Security 1.1 ist SignBeforeEncryptAndEncryptSignature der Standardwert.  SignBeforeEncrypt ist der Standardwert mit WS-Security 1.0.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|`messageSecurityVersion`|Legt die verwendete Version von WS-Security fest. Folgende Werte sind gültig:<br /><br /> -   WSSecurityJan2004<br />-   WSSecurityXXX2005<br /><br /> Der Standardwert ist WSSecurityXXX2005. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.|  
|`requireDerivedKeys`|Ein boolescher Wert, der angibt, ob Schlüssel von den Originalprüfschlüsseln abgeleitet werden können. Die Standardeinstellung ist `true`.|  
|`requireSecurityContextCancellation`|Ein boolescher Wert, der angibt, ob ein nicht mehr benötigter Sicherheitskontext abgebrochen und beendet werden soll. Die Standardeinstellung ist `true`.|  
|`requireSignatureConfirmation`|Ein boolescher Wert, der angibt, ob die WS-Security-Signaturbestätigung aktiviert ist. Bei der Einstellung `true` werden Nachrichtensignaturen vom Beantworter bestätigt. Die Standardeinstellung ist `false`.<br /><br /> Mit der Signaturbestätigung wird bestätigt, dass der Dienst unter vollständiger Berücksichtigung einer Anforderung antwortet.|  
|`securityHeaderLayout`|Gibt die Reihenfolge der Elemente im Sicherheitsheader an. Gültige Werte sind:<br /><br /> -Strict. Gemäß dem Prinzip „declare before use“ werden die Elemente deklariert, bevor sie dem Sicherheitsheader hinzugefügt werden.<br />-Lax. Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge hinzugefügt gemäß der WSS: SOAP Message Security-Spezifikation.<br />-LaxWithTimestampFirst. Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge hinzugefügt gemäß der WSS: SOAP Message Security, nur dass das erste Element im Sicherheitsheader ein wsse:Timestamp-Element sein muss.<br />-LaxWithTimestampLast. Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge hinzugefügt gemäß der WSS: SOAP Message Security, nur dass das letzte Element im Sicherheitsheader ein wsse:Timestamp-Element sein muss.<br /><br /> Standardwert ist Strict.<br /><br /> Dieses Element ist vom Typ <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Gibt ein aktuell ausgegebenes Token an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings>](../../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)|Legt die Sicherheitseinstellungen für einen lokalen Client für diese Bindung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings>](../../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)|Legt die Sicherheitseinstellungen für einen lokalen Dienst für diese Bindung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicherheit mit benutzerdefinierten Bindungen](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
