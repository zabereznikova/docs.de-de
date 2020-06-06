---
title: <secureConversationBootstrap>
ms.date: 03/30/2017
ms.assetid: 66b46f95-fa2d-4b5b-b6ce-0572ab0cdd50
ms.openlocfilehash: b3187cb51b6fd32797c9ad401c704d5f16c6f7e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399914"
---
# \<secureConversationBootstrap>
Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationBootstrap>**  
  
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
  
## <a name="type"></a>type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`allowSerializedSigningTokenOnReply`|Optional. Ein boolescher Wert, der angibt, ob ein serialisiertes Token für eine Antwort verwendet werden kann. Der Standardwert ist `false`. Beim Verwenden einer Dualbindung ist `true` die Standardeinstellung, vorgenommene Einstellungen werden ignoriert.|  
|`authenticationMode`|Gibt den SOAP-Authentifizierungsmodus an, der zwischen Initiator und Beantworter verwendet wird.<br /><br /> Der Standardwert ist sspiNegotiated.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Configuration.AuthenticationMode>.|  
|`defaultAlgorithmSuite`|Die Sicherheitsalgorithmussammlung definiert verschiedene Algorithmen, wie zum Beispiel Kanonisierung, Digest, KeyWrap, Signatur, Verschlüsselung und KeyDerivation. Jede Sicherheitsalgorithmussammlung definiert Werte für diese verschiedenen Parameter. Die nachrichtenbasierte Sicherheit wird über diese Algorithmen sichergestellt.<br /><br /> Dieses Attribut wird verwendet, wenn mit einer anderen Plattform gearbeitet wird, die eine Reihe von Nicht-Standardalgorithmen verwendet. Sie sollten die Stärken und Schwächen der relevanten Algorithmen kennen, wenn Sie Änderungen an dieser Einstellung vornehmen. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. Der Standardwert lautet `Basic256`.|  
|`includeTimestamp`|Ein boolescher Wert, der angibt, ob jede Nachricht einen Zeitstempel enthält. Der Standardwert lautet `true`.|  
|`keyEntropyMode`|Gibt an, wie Schlüssel für das Sichern von Nachrichten berechnet werden. Schlüssel können nur auf dem Schlüsselmaterial des Clients, des Diensts oder auf einer Kombination von beiden basiert werden. Gültige Werte sind:<br /><br /> -ClientEntropy: der Sitzungsschlüssel basiert auf dem vom Client bereitgestellten Schlüsselmaterial.<br />-ServerEntropy: der Sitzungsschlüssel basiert auf dem vom Dienst bereitgestellten Schlüsselmaterial.<br />-CombinedEntropy: der Sitzungsschlüssel basiert auf dem vom Client und vom Dienst bereitgestellten Schlüsselmaterial.<br /><br /> Der Standardwert ist CombinedEntropy.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`messageProtectionOrder`|Legt die Reihenfolge fest, in der Sicherheitsalgorithmen der Nachrichtenebene auf die Nachricht angewendet werden. Gültige Werte sind:<br /><br /> -Signbeforeverschlüsseln: Zuerst signieren, dann verschlüsseln.<br />-Signbeforeverschlüsseltandverschlüsseltsignature: Signieren, verschlüsseln und Verschlüsseln der Signatur.<br />-Verschlüsseltbeforesign: zuerst verschlüsseln, dann signieren.<br /><br /> Beim Verwenden von gegenseitigen Zertifikaten mit WS-Security 1.1 ist SignBeforeEncryptAndEncryptSignature der Standardwert.  SignBeforeEncrypt ist der Standardwert mit WS-Security 1.0.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|`messageSecurityVersion`|Legt die verwendete Version von WS-Security fest. Gültige Werte sind:<br /><br /> - WSSecurityJan2004<br />-WSSecurityXXX2005<br /><br /> Der Standardwert ist WSSecurityXXX2005. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.|  
|`requireDerivedKeys`|Ein boolescher Wert, der angibt, ob Schlüssel von den Originalprüfschlüsseln abgeleitet werden können. Der Standardwert lautet `true`.|  
|`requireSecurityContextCancellation`|Ein boolescher Wert, der angibt, ob ein nicht mehr benötigter Sicherheitskontext abgebrochen und beendet werden soll. Der Standardwert lautet `true`.|  
|`requireSignatureConfirmation`|Ein boolescher Wert, der angibt, ob die WS-Security-Signaturbestätigung aktiviert ist. Bei der Einstellung `true` werden Nachrichtensignaturen vom Beantworter bestätigt. Der Standardwert lautet `false`.<br /><br /> Mit der Signaturbestätigung wird bestätigt, dass der Dienst unter vollständiger Berücksichtigung einer Anforderung antwortet.|  
|`securityHeaderLayout`|Gibt die Reihenfolge der Elemente im Sicherheitsheader an. Gültige Werte sind:<br /><br /> Strengeren. Gemäß dem Prinzip „declare before use“ werden die Elemente deklariert, bevor sie dem Sicherheitsheader hinzugefügt werden.<br />Lockerer. Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge gemäß der WSS: SOAP Message Security-Spezifikation hinzugefügt.<br />-Laxwithtimestampfirst. Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge gemäß der WSS: SOAP Message Security-Spezifikation hinzugefügt. Ausnahme: Das erste Element im Sicherheitsheader muss ein wsse:Timestamp-Element sein.<br />-Laxwithtimestamplast. Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge gemäß der WSS: SOAP Message Security-Spezifikation hinzugefügt. Ausnahme: Das letzte Element im Sicherheitsheader muss ein wsse:Timestamp-Element sein.<br /><br /> Standardwert ist Strict.<br /><br /> Dieses Element ist vom Typ <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Gibt ein aktuell ausgegebenes Token an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings>](localclientsettings-element.md)|Legt die Sicherheitseinstellungen für einen lokalen Client für diese Bindung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings>](localservicesettings-element.md)|Legt die Sicherheitseinstellungen für einen lokalen Dienst für diese Bindung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicherheit mit benutzerdefinierten Bindungen](../../../wcf/samples/custom-binding-security.md)
