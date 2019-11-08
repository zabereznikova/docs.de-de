---
title: <msmqIntegrationBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- msmqIntegrationBinding Element
ms.assetid: edf277f3-e3bf-4ed8-9f55-83b5788430a7
ms.openlocfilehash: 95942e9818eccc018c123148949c6f2dee4fa6e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736623"
---
# <a name="msmqintegrationbinding"></a>\<"MsmqIntegrationBinding" >
Definiert eine Bindung, die eine Warteschlangenunterstützung bereitstellt, indem Nachrichten über MSMQ weitergeleitet werden.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<"MsmqIntegrationBinding" >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<msmqIntegrationBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveContextEnabled="Boolean"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           serializationFormat="XML/Binary/ActiveX/ByteArray/Stream"
           timeToLive="TimeSpan"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|closeTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|customDeadLetterQueue|Ein URI, der den Speicherort der Warteschlange für unzustellbare Nachrichten für jede Anwendung enthält, in der abgelaufene oder nicht übertragene oder nicht zugestellte Nachrichten platziert werden.<br /><br /> Die Warteschlange für unzustellbare Nachrichten ist eine Warteschlange für abgelaufene Nachrichten, die nicht zugestellt werden konnten. Diese Warteschlange befindet sich im Warteschlangen-Manager der sendenden Anwendung.<br /><br /> Der URI, der von <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> angegeben wird, muss das net.msmq-Schema verwenden.|  
|deadLetterQueue|Ein <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>-Wert, der den ggf. zu verwendenden Typ der Warteschlange für unzustellbare Nachrichten angibt.<br /><br /> Die Warteschlange für unzustellbare Nachrichten ist der Speicherort für Nachrichten, die nicht zugestellt werden konnten.<br /><br /> Bei Nachrichten, die exactlyOnce-Zusicherung erfordern (das heißt, das `exactlyOnce`-Attribut ist auf `true` festgelegt), ist dieses Attribut standardmäßig die systemweite Transaktionswarteschlange für unzustellbare Nachrichten in MSMQ.<br /><br /> Für Nachrichten, die keine Zusicherung erfordern, ist dieses Attribut standardmäßig `null`.|  
|durable|Ruft einen booleschen Wert ab, der angibt, ob die Nachricht in der Warteschlange dauerhaft oder flüchtig ist. Eine permanente Meldung überlebt einen Warteschlangen-Managerabsturz, was für eine flüchtige Meldung nicht gilt. Flüchtige Nachrichten sind nützlich, wenn Anwendungen eine geringere Latenz erfordern und eine geringe Anzahl verlorener Nachrichten tolerieren können. Wenn für das `exactlyOnce`-Attribut `true` festgelegt wird, müssen die Nachrichten dauerhaft sein. Der Standardwert ist `true`.|  
|exactlyOnce|Ein boolescher Wert, der angibt, ob jede Nachricht nur einmal zugestellt wird. Der Absender wird dann über den Zustellfehler benachrichtigt. Wenn der `durable`-Wert `false` ist, wird dieses Attribut ignoriert, und es werden Nachrichten ohne Zustellungszusicherung übertragen. Der Standardwert ist `true`. Weitere Informationen finden Sie unter <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.|  
|maxReceivedMessageSize|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Byte einschließlich Header angibt, die von dieser Bindung verarbeitet wird. Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standard ist 65536. Auf diese Weise sollen Denial-of-Service-Angriffe (DoS) reduziert werden.|  
|MaxRetryCycles|Eine ganze Zahl, die die Anzahl der Wiederholungszyklen für die Funktion zur Erkennung nicht verarbeitbarer Nachrichten angibt. Eine Nachricht gilt als nicht verarbeitbare Nachricht, wenn alle erneuten Zustellversuche fehlgeschlagen sind. Der Standardwert ist&#160;2. Weitere Informationen finden Sie unter <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.|  
|Name|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|receiveErrorHandling|Ein <xref:System.ServiceModel.ReceiveErrorHandling>-Wert, der angibt, wie nicht verarbeitbare und nicht zustellbare Nachrichten behandelt werden.|  
|receiveRetryCount|Eine ganze Zahl, die die maximale Anzahl von sofortigen Wiederholungsversuchen festlegt, die dem Warteschlangen-Manager zum Senden zur Verfügung steht, wenn die Übertragung einer Nachricht zur Anwendung fehlschlägt.<br /><br /> Wenn die maximale Anzahl der Zustellungsversuche erreicht ist und die Nachricht nicht von der Anwendung empfangen wurde, wird die Nachricht an eine Wiederholungswarteschlange gesendet, um sie später erneut zuzustellen. Das Zeitintervall, nach dem die Nachricht zurück in die sendende Warteschlange übertragen wird, wird durch `retryCycleDelay` gesteuert Wenn die Wiederholungszyklen den `maxRetryCycles`-Wert erreichen, wird die Nachricht entweder an die Warteschlange für potenziell schädliche Nachrichten gesendet, oder es wird eine negative Bestätigung zurück zum Absender geschickt.|  
|receiveTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|  
|receiveContextEnabled|Ein boolescher Wert, der angibt, ob Empfangskontext zum Verarbeiten von Nachrichten in Warteschlangen aktiviert ist. Wenn dies auf `true`festgelegt ist, kann ein Dienst eine Nachricht in der Warteschlange einsehen, um mit der Verarbeitung zu beginnen, und wenn ein Fehler auftritt und eine Ausnahme ausgelöst wird, verbleibt er in der Warteschlange. Dienste können Nachrichten auch "Sperren", um den Verarbeitungs Versuch zu einem späteren Zeitpunkt zu wiederholen. ReceiveContext stellt einen Mechanismus bereit, mit dem die Nachricht nach der Verarbeitung "vervollständigt" wird, damit Sie aus der Warteschlange entfernt werden kann. Nachrichten werden nicht mehr gelesen und in Warteschlangen über das Netzwerk umgeschrieben, und einzelne Nachrichten werden während der Verarbeitung nicht über verschiedene Dienst Instanzen hinweg überspringt.|  
|retryCycleDelay|Ein TimeSpan-Wert, der die Zeitverzögerung zwischen den Wiederholungszyklen angibt, wenn versucht wird, eine Nachricht zuzustellen, die nicht sofort zugestellt werden konnte. Der Wert definiert nur die Mindestwartezeit, da die tatsächliche Wartezeit länger sein kann. Der Standardwert ist 00:30:00. Weitere Informationen finden Sie unter <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.|  
|sendTimeout|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|serializationFormat|Definiert das für die Serialisierung des Nachrichtentexts verwendete Format. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat>.|  
|timeToLive|Ein TimeSpan-Wert, der angibt, wie lange die Nachricht gültig ist, bis sie abläuft und in die Warteschlange für unzustellbare Nachrichten übertragen wird. Der Standardwert ist 1.00:00:00.<br /><br /> Dieses Attribut wird festgelegt, um sicherzustellen, dass zeitkritische Nachrichten nicht veralten, bevor sie von den empfangenden Anwendungen verarbeitet werden. Eine Nachricht in einer Warteschlange, die nicht von der empfangenden Anmeldung innerhalb des angegebenen Zeitintervalls verarbeitet wird, läuft ab. Abgelaufene Nachrichten werden an eine besondere Warteschlange gesendet: die Warteschlange für unzustellbare Nachrichten. Der Speicherort der Warteschlange für unzustellbare Meldungen wird mithilfe des `DeadLetterQueue`-Attributs festgelegt. Andernfalls gilt die entsprechende, auf den Zusicherungen basierende Standardeinstellung.|  
|useMsmqTracing|Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichten verfolgt werden sollen. Der Standardwert ist `false`. Wenn die Ablaufverfolgung aktiviert ist, werden Berichtsnachrichten erstellt und jedes Mal an die Berichtswarteschlange gesendet, wenn die Nachricht einen Computer mit Message Queuing erreicht oder verlässt.|  
|useSourceJournal|Ein boolescher Wert, der angibt, ob Kopien der von dieser Bindung verarbeiteten Nachrichten in der Quelljournalwarteschlange gespeichert werden sollen. Der Standardwert ist `false`.<br /><br /> Anwendungen in Warteschlangen, die Nachrichten aufzeichnen möchten, die die Ausgangswarteschlange des Computers verlassen haben, können die Nachrichten in eine Journalwarteschlange kopieren. Wenn eine Nachricht die Ausgangswarteschlange verlässt und eine Bestätigung empfangen wird, dass die Nachricht auf dem Zielcomputer empfangen wurde, wird eine Kopie der Nachricht in der Systemjournalwarteschlange des sendenden Computers beibehalten.|  
  
## <a name="serializationformat-attribute"></a>{serializationFormat}-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Xml|XML-Format|  
|Binär|Binärformat|  
|ActiveX|ActiveX-Format|  
|ByteArray|Serialisiert das Objekt in Byte-Array.|  
|Stream|Der Text, als Stream formatiert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Security >](security-of-msmqintegrationbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<-Bindungen >](bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Bindungs Element kann verwendet werden, um Windows Communication Foundation (WCF)-Anwendungen zu ermöglichen, Nachrichten an vorhandene MSMQ-Anwendungen zu senden und von diesen zu empfangen, die com, MSMQ Native APIs oder die im <xref:System.Messaging?displayProperty=nameWithType> Namespace definierten Typen verwenden, die Sie verwenden können. Dieses Konfigurationselement gibt an, wie die Adressen der Warteschlange adressiert werden, ob übertragen werden soll, ob Nachrichten dauerhaft gespeichert werden müssen und wie Nachrichten geschützt und authentifiziert werden sollen. Weitere Informationen finden Sie unter Vorgehens [Weise: Austauschen von Nachrichten mit WCF-Endpunkten und Message Queuing Anwendungen](../../../wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).  
  
## <a name="example"></a>Beispiel  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <msmqIntegrationBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxImmediateRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 useSourceJournal="true"
                 useMsmqTracing="true"
                 serializationFormat="Binary">
          <security mode="None" />
        </binding>
      </msmqIntegrationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>
- [\<binding >](bindings.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [Warteschlangen in WCF](../../../wcf/feature-details/queues-in-wcf.md)
