---
title: <localServiceSettings>-Element
ms.date: 03/30/2017
ms.assetid: 0658549c-3f65-46dd-8c5c-9895441ed734
ms.openlocfilehash: 3043c07afd316d90cc5525a67bef144f33d9b136
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204930"
---
# <a name="localservicesettings-element"></a>\<localServiceSettings>-Element

Legt die Sicherheitseinstellungen für einen lokalen Dienst für diese Bindung fest.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localServiceSettings>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security>
  <localServiceSettings detectReplays="Boolean"
                        inactivityTimeout="TimeSpan"
                        issuedCookieLifeTime="TimeSpan"
                        maxCachedCookies="Integer"
                        maxClockSkew="TimeSpan"
                        maxPendingSessions="Integer"
                        maxStatefulNegotiations="Integer"
                        negotiationTimeout="TimeSpan"
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
|`detectReplays`|Ein boolescher Wert, der angibt, ob Replay-Angriffe auf den Kanal automatisch erkannt und behandelt werden. Der Standardwert lautet `false`.|  
|`inactivityTimeout`|Ein positiver Wert <xref:System.TimeSpan> , der die Dauer der Inaktivität angibt, die der Kanal wartet, bevor ein Timeout auftritt. Der Standardwert ist "01:00:00".|  
|`issuedCookieLifeTime`|Eine <xref:System.TimeSpan>, die die Lebensdauer angibt, die für alle neuen Sicherheitscookies ausgegeben wird. Cookies, die ihre Lebensdauer übersteigen, werden wiederverwendet und müssen erneut ausgehandelt werden. Der Standardwert ist "10:00:00".|  
|`maxCachedCookies`|Eine positive ganze Zahl, die die maximale Anzahl an Cookies angibt, die zwischengespeichert werden können. Der Standardwert lautet 1000.|  
|`maxClockSkew`|Eine <xref:System.TimeSpan>, die den maximal zulässigen Zeitunterschied zwischen den Systemuhren der beiden Kommunikationspartner angibt. Der Standardwert ist "00:05:00".<br /><br /> Wenn dieser Wert auf den Standardwert festgelegt wird, akzeptiert der Empfänger Nachrichten mit Sendezeitstempeln, die bis zu 5 Minuten vor oder nach dem Zeitpunkt liegen, zu dem die Nachricht empfangen wurde. Nachrichten, die den Sendezeittest nicht bestehen, werden verworfen. Diese Einstellung wird in Verbindung mit dem `replayWindow`-Attribut verwendet.|  
|`maxPendingSessions`|Eine positive ganze Zahl, die die maximale Anzahl an ausstehenden Sicherheitssitzungen angibt, die der Dienst unterstützt. Wenn diese Grenze erreicht wird, erhalten alle neuen Clients SOAP-Fehler. Der Standardwert lautet „1000“.|  
|`maxStatefulNegotiations`|Eine positive ganze Zahl, die die Anzahl von Sicherheitsaushandlungen angibt, die gleichzeitig aktiv sein können. Aushandlungssitzungen, die über dem Grenzwert liegen, werden in die Warteschlange gestellt und können erst dann fertig gestellt werden, wenn wieder Speicherplatz verfügbar wird. Der Standardwert ist 1024.|  
|`negotiationTimeout`|Eine <xref:System.TimeSpan>, die die Lebensdauer der vom Kanal verwendeten Sicherheitsrichtlinie angibt. Wenn die Zeitspanne abgelaufen ist, handelt der Kanal mit dem Client eine neue Sicherheitsrichtlinie aus. Der Standardwert ist "00:02:00".|  
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

 Die Einstellungen sind lokal, da sie nicht als Teil der Sicherheitsrichtlinie des Diensts veröffentlicht werden und nicht die Client-Bindung beeinträchtigen.  
  
 Die folgenden Attribute des `localServiceSecuritySettings`-Elements können helfen, einen Denial-of-Service-Sicherheitsangriff (DoS) zu verhindern:  
  
- `maxCachedCookies`: Steuert die maximale Anzahl zeitlich begrenzter SecurityContextTokens, die der Server nach einer SPNEGO-Aushandlung oder SSL-Aushandlung zwischenspeichert.  
  
- `issuedCookieLifetime`: Steuert die Lebensdauer der SecurityContextTokens, die der Server nach der SPNEGO-Aushandlung oder SSL-Aushandlung ausstellt. Der Server speichert die SecurityContextTokens für diesen Zeitraum zwischen.  
  
- `maxPendingSessions`: Steuert die maximale Anzahl sicherer Konversationen, die auf dem Server erstellt werden, für die jedoch keine Anwendungsnachrichten verarbeitet wurden. Dieses Kontingent verhindert, dass Clients sichere Konversationen auf dem Dienst erstellen, sodass der Dienst den Zustand für jeden Client beibehält, sie jedoch nicht verwendet.  
  
- `inactivityTimeout`: Steuert die maximale Zeit, die der Dienst eine sichere Konversation aufrechterhält, ohne eine Anwendungsnachricht zu erhalten. Dieses Kontingent verhindert, dass Clients sichere Konversationen auf dem Dienst erstellen, sodass der Dienst den Zustand für jeden Client beibehält, sie jedoch nicht verwendet.  
  
 In einer sicheren Konversationssitzung haben sowohl das `inactivityTimeout`-Attribut als auch das `receiveTimeout`-Attribut der Bindung Auswirkungen auf das Sitzungstimeout. Der kürzere der beiden Werte bestimmt, wann das Timeout eintritt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicherheit mit benutzerdefinierten Bindungen](../../../wcf/samples/custom-binding-security.md)
