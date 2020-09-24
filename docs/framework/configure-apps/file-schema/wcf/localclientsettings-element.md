---
title: <localClientSettings>-Element
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: 19eaea71fdaad1b945524cca5cf15634e0b0fa14
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158733"
---
# <a name="localclientsettings-element"></a>\<localClientSettings>-Element

Legt die Sicherheitseinstellungen für einen lokalen Client für diese Bindung fest.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localClientSettings>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security>
   <localClientSettings cacheCookies="Boolean"
                        cookieRenewalThresholdPercentage="Integer"
                        detectReplays="Boolean"
                        maxClockSkew="TimeSpan"
                        maxCookieCachingTime="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`cacheCookies`|Ein boolescher Wert, der angibt, ob die Cookiezwischenspeicherung aktiviert ist. Der Standardwert lautet `false`.|  
|`cookieRenewalThresholdPercentage`|Eine ganze Zahl, die den maximalen Prozentsatz an Cookies angibt, die erneuert werden können. Dieser Wert sollte zwischen 0 und einschließlich 100 liegen. Der Standard ist 90.|  
|`detectReplays`|Ein boolescher Wert, der angibt, ob Replay-Angriffe auf den Kanal automatisch erkannt und behandelt werden. Der Standardwert lautet `false`.|  
|`maxClockSkew`|Eine <xref:System.TimeSpan>, die den maximal zulässigen Zeitunterschied zwischen den Systemuhren der beiden Kommunikationspartner angibt. Der Standardwert ist "00:05:00".<br /><br /> Wenn dieser Wert auf den Standardwert festgelegt wird, akzeptiert der Empfänger Nachrichten mit Sendezeitstempeln, die bis zu 5 Minuten vor oder nach dem Zeitpunkt liegen, zu dem die Nachricht empfangen wurde. Nachrichten, die den Sendezeittest nicht bestehen, werden verworfen. Diese Einstellung wird in Verbindung mit dem `replayWindow`-Attribut verwendet.|  
|`maxCookieCachingTime`|Eine <xref:System.TimeSpan>, die die maximale Lebensdauer von Cookies angibt. Der Standardwert ist "10675199.02:48:05.4775807".|  
|`reconnectTransportOnFailure`|Ein boolescher Wert, der angibt, ob Verbindungen, die WS-Reliable-Messaging verwenden, nach Transportfehlern erneut versuchen, eine Verbindung herzustellen. Der Standard ist `true`, was bedeutet, dass unendlich viele Versuche der Verbindungsherstellung durchgeführt werden. Dieser Kreislauf wird vom Inaktivitätstimeout unterbrochen, das dazu führt, dass der Kanal eine Ausnahme ausgibt, wenn die Verbindung nicht wiederhergestellt werden kann.|  
|`replayCacheSize`|Eine positive ganze Zahl, die die Anzahl der zwischengespeicherten Nonces für die Replay-Erkennung angibt. Wenn dieses Limit überschritten wird, wird die älteste Nonce entfernt, und eine neue Nonce für die neue Nachricht wird erstellt. Der Standardwert ist 500000.|  
|`replayWindow`|Eine <xref:System.TimeSpan>, die die Dauer angibt, in der einzelne Nachrichtennonces gültig sind.<br /><br /> Nach dieser Zeitspanne wird eine Nachricht mit derselben Nonce wie die zuvor gesendete nicht akzeptiert. Dieses Attribut wird in Verbindung mit dem `maxClockSkew`-Attribut verwendet, um Replay-Angriffe zu verhindern. Ein Angreifer kann eine Nachricht wiederholen, nachdem das Wiederholungsfenster abgelaufen ist. Die Nachricht besteht jedoch den `maxClockSkew`-Test nicht, der Nachrichten mit Zeitstempeln bis zu einem bestimmten Zeitpunkt vor oder nach dem Empfang der Nachricht zurückweist.|  
|`sessionKeyRenewalInterval`|Eine <xref:System.TimeSpan>, die angibt, nach welchem Zeitraum der Initiator den Schlüssel für die Sicherheitssitzung erneuert. Der Standardwert ist "10:00:00".|  
|`sessionKeyRolloverInterval`|Eine <xref:System.TimeSpan>, die das Zeitintervall angibt, während dem ein früherer Sitzungsschlüssel während der Schlüsselerneuerung für eingehende Nachrichten gültig ist. Der Standardwert ist "00:05:00".<br /><br /> Während der Erneuerung des Schlüssels müssen Nachrichten vom Client und vom Server mit dem aktuellsten Schlüssel gesendet werden. Eingehende Nachrichten, die mit dem früheren Sitzungsschlüssel gesichert sind, werden von beiden Seiten bis zum Ablauf der Übergangszeit akzeptiert.|  
|`timestampValidityDuration`|Eine positive <xref:System.TimeSpan>, die die Dauer angibt, in der ein Zeitstempel gültig ist. Der Standardwert ist "00:15:00".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.|  
  
## <a name="remarks"></a>Bemerkungen  

 Die Einstellungen sind lokal, da sie nicht von der Sicherheitsrichtlinie des Diensts abgeleitet werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicherheit mit benutzerdefinierten Bindungen](../../../wcf/samples/custom-binding-security.md)
