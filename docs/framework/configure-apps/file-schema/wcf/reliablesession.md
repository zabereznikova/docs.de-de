---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: ec69d9194d98302a4744e290f23fbb150b2e87cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181312"
---
# \<reliableSession>

Definiert die Einstellung für WS-Reliable Messaging. Wenn dieses Element einer benutzerdefinierten Bindung hinzugefügt wird, kann der resultierende Kanal ExactlyOnce-Zustellungszusicherungen unterstützen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<reliableSession>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|acknowledgementInterval|Eine <xref:System.TimeSpan>, die angibt, wie lange der Kanal maximal wartet, bis eine Bestätigung für die bis zu diesem Zeitpunkt erhaltenen Nachrichten gesendet wird. Der Standardwert ist 00:00:0.2.|  
|flowControlEnabled|Eine boolescher Wert, der angibt, ob die erweiterte Flusssteuerung, eine Microsoft-spezifische Implementierung der Flusssteuerung für WS-Reliable Messaging, aktiviert ist. Der Standardwert lautet `true`.|  
|inactivityTimeout|Eine <xref:System.TimeSpan>, die die maximale Dauer angibt, die der Kanal dem anderen Kommunikationsteilnehmer für das ausbleibende Senden von Nachrichten einräumt, bevor im Kanal ein Fehler ausgelöst wird. Der Standardwert ist 00:10:00.<br /><br /> Aktivität auf einem Kanal wird als Empfang einer Anwendungs- oder Infrastrukturnachricht definiert. Diese Eigenschaft steuert die maximale Menge an Zeit, um eine inaktive Sitzung am Leben zu erhalten. Bei längeren Zeiten ohne Aktivität wird die Sitzung durch die Infrastruktur beendet, und im Kanal wird ein Fehler ausgelöst. **Hinweis:**  Es ist nicht erforderlich, dass die Anwendung regelmäßig Nachrichten sendet, um die Verbindung aufrechtzuerhalten.|  
|maxPendingChannels|Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Listener warten können, um akzeptiert zu werden. Dieser Wert sollte zwischen 1 und einschließlich 16384 liegen. Der Standardwert ist 4.<br /><br /> Kanäle sind ausstehend, wenn sie darauf warten, akzeptiert zu werden. Wenn dieser Grenzwert einmal erreicht ist, werden keine Kanäle erstellt. Sie werden dagegen in den ausstehenden Modus versetzt, bis diese Zahl sinkt (durch das Akzeptieren ausstehender Kanäle). Dieser Grenzwert wird pro Factory festgelegt.<br /><br /> Wenn der Schwellenwert erreicht wird und eine Remoteanwendung versucht, eine neue zuverlässige Sitzung herzustellen, wird die Anforderung abgelehnt und der Öffnungsvorgang, der dies angefordert hat, schlägt fehl. Dieser Grenzwert gilt nicht für die Anzahl an ausstehenden ausgehenden Kanälen.|  
|maxRetryCount|Eine ganze Zahl, die angibt, wie oft ein zuverlässiger Kanal maximal versucht, eine Nachricht, für die keine Bestätigung empfangen wurde, erneut zu übertragen (durch Aufrufen von Send im zugrunde liegenden Kanal).<br /><br /> Dieser Wert muss größer als null sein. Der Standard ist 8.<br /><br /> Dieser Wert sollte eine ganze Zahl größer null sein. Wenn nach der letzten Übertragung keine Bestätigung empfangen wurde, tritt ein Fehler im Kanal auf.<br /><br /> Eine Nachricht wird als übertragen betrachtet, wenn die Zustellung vom Empfänger bestätigt wurde.<br /><br /> Wenn die Bestätigung nicht innerhalb einer bestimmten Zeit eingegangen ist, überträgt die Infrastruktur die Nachricht automatisch neu. Die Infrastruktur versucht die Nachricht maximal so oft erneut zu senden, wie durch diese Eigenschaft festgelegt. Wenn nach der letzten Übertragung keine Bestätigung empfangen wurde, tritt ein Fehler im Kanal auf.<br /><br /> Die Infrastruktur verwendet einen exponentiellen Backoff-Algorithmus um den Zeitpunkt für die Neuübertragung zu ermitteln. Dabei wird eine berechnete durchschnittliche Round Trip Time zugrunde gelegt. Der Zeitpunkt liegt zunächst 1 Sekunde vor der Neuübertragung. Bei jedem erneuten Versuch wird die Verzögerung verdoppelt. Zwischen dem ersten Übertragungsversuch und dem letzten Übertragungsversuch liegen somit ca. 8,5 Minuten. Der Zeitpunkt für den ersten Neuübertragungsversuch wird gemäß der berechneten Round Trip Time angepasst, und die daraus resultierende Zeitspanne für die Übertragungsversuche variiert entsprechend. Dadurch können die Zeitpunkte für die Neuübertragung dynamisch an die unterschiedlichen Netzwerkbedingungen angepasst werden.|  
|maxTransferWindowSize|Eine ganze Zahl, die die maximale Größe des Puffers angibt. Gültige Werte reichen von 1 bis 4096 einschließlich.<br /><br /> Auf dem Client definiert dieses Attribut die maximale Größe des Puffers, in dem ein zuverlässiger Kanal die noch nicht vom Empfänger bestätigten Nachrichten speichert. Die Einheit dieses Kontingents ist eine Nachricht. Ist der Puffer voll, werden weitere SEND-Vorgänge blockiert.<br /><br /> Beim Empfänger definiert dieses Attribut die maximale Größe des Puffers, in dem ein Kanal eingehende Nachrichten speichert, die noch nicht an die Anwendung zugestellt wurden. Ist der Puffer voll, werden weitere Nachrichten vom Empfänger automatisch verworfen und müssen vom Client erneut übertragen werden.|  
|geordnete|Ein boolescher Wert, der angibt, ob Nachrichten auf jeden Fall in der Reihenfolge ihres Versands eintreffen. Lautet diese Einstellung `false`, können Nachrichten außerhalb der Reihenfolge eintreffen. Der Standardwert lautet `true`.|  
|reliableMessagingVersion|Ein gültiger Wert von <xref:System.ServiceModel.ReliableMessagingVersion>, der die zu verwendende WS-ReliableMessaging-Version angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Bemerkungen  

 Zuverlässige Sitzungen bieten Funktionen für zuverlässiges Messaging. Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen, wie Prüfung der Nachrichtenreihenfolge beim Eingang, vorgenommen. Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht. Dieses Element stellt auch optional sortierte Nachrichtenübermittlung bereit. Diese implementierte Sitzung kann SOAP und Transportvermittler überqueren.  
  
 Jedes Bindungselement stellt einen Verarbeitungsschritt beim Senden und Empfangen von Nachrichten dar. Zur Laufzeit erstellen Bindungselemente die Kanalfactorys und die Listener, die notwendig sind, um ausgehende und eingehende Kanalstapel zum Senden und Empfangen von Nachrichten zu erstellen. Das `reliableSession` bietet eine optionale Ebene im Stapel, die eine zuverlässige Sitzung zwischen Endpunkten herstellen und das Sitzungsverhalten konfigurieren kann.  
  
 Weitere Informationen finden Sie unter [zuverlässige Sitzungen](../../../wcf/feature-details/reliable-sessions.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie eine benutzerdefinierte Bindung mit verschiedenen Transport- und Codierungselementen konfiguriert wird, insbesondere durch zuverlässige Sitzungen, die den Clientstatus aufrechterhalten und Zustellungszusicherungen anhand der Nachrichtenreihenfolge vorgeben. Diese Funktion wird in den Anwendungskonfigurationsdateien für den Client und den Dienst konfiguriert. Im Beispiel wird die Dienstkonfiguration gezeigt.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [Zuverlässige Sitzungen](../../../wcf/feature-details/reliable-sessions.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
