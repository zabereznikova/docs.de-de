---
title: '&lt;netMsmqBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f0c8f0d2f9ed2471fab2eda17c7d9f9be5b77c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetmsmqbindinggt"></a>&lt;netMsmqBinding&gt;
Definiert eine Bindung in der Warteschlange, die für eine computerübergreifende Kommunikation geeignet ist.  
  
 \<System. ServiceModel >  
\<Bindungen >  
\<NetMsmqBinding >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netMsmqBinding>  
    <binding   
       closeTimeout="TimeSpan"   
       customDeadLetterQueue="Uri"  
       deadLetterQueue="Uri"  
       durable="Boolean"  
       exactlyOnce="Boolean"   
       maxBufferPoolSize="Integer"  
       maxReceivedMessageSize"Integer"  
       maxRetryCycles="Integer"   
       name="string"   
       openTimeout="TimeSpan"   
       poisonMessageHandling="Disabled/EnabledIfSupported"   
       queueTransferProtocol="Native/Srmp/SrmpSecure"  
       receiveErrorHandling="Drop/Fault/Move/Reject"  
       receiveTimeout="TimeSpan"   
       receiveRetryCount="Integer"  
       rejectAfterLastRetry="Boolean"   
       retryCycleDelay="TimeSpan"    
       sendTimeout="TimeSpan"   
       timeToLive="TimeSpan"    
       useActiveDirectory="Boolean"  
       useMsmqTracing="Boolean  
       useSourceJournal="Boolean"  
          <security>  
                  <message    
                        algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/InfoCard "/>  
                  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />   </binding></netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`customDeadLetterQueue`|Ein URI, der den Speicherort der Warteschlange für unzustellbare Nachrichten für jede Anwendung enthält, in der abgelaufene oder nicht übertragene oder nicht zugestellte Nachrichten platziert werden.<br /><br /> Die Warteschlange für unzustellbare Nachrichten ist eine Warteschlange für abgelaufene Nachrichten, die nicht zugestellt werden konnten. Diese Warteschlange befindet sich im Warteschlangen-Manager der sendenden Anwendung.<br /><br /> Der URI, der von <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> angegeben wird, muss das net.msmq-Schema verwenden.|  
|`deadLetterQueue`|Ein <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>-Wert, der den ggf. zu verwendenden Typ der Warteschlange für unzustellbare Nachrichten angibt.<br /><br /> Die Warteschlange für unzustellbare Nachrichten ist eine Warteschlange für Nachrichten, die nicht zugestellt werden konnten.<br /><br /> Bei Nachrichten, die `exactlyOnce`-Zusicherung erfordern (das heißt, das `exactlyOnce`-Attribut ist auf `true` gesetzt), ist dieses Attribut standardmäßig die systemweite Transaktionswarteschlange für unzustellbare Nachrichten in MSMQ.<br /><br /> Für Nachrichten, die keine Zusicherung erfordern, ist dieses Attribut standardmäßig `null`.|  
|`durable`|Ruft einen booleschen Wert ab, der angibt, ob die Nachricht in der Warteschlange dauerhaft oder flüchtig ist. Eine permanente Meldung überlebt einen Warteschlangen-Managerabsturz, was für eine flüchtige Meldung nicht gilt. Flüchtige Nachrichten sind nützlich, wenn Anwendungen eine geringere Latenz erfordern und eine geringe Anzahl verlorener Nachrichten tolerieren können. Wenn für das `exactlyOnce`-Attribut `true` festgelegt wird, müssen die Nachrichten dauerhaft sein. Die Standardeinstellung ist `true`.|  
|`exactlyOnce`|Ein boolescher Wert, der angibt, ob die von dieser Bindung verarbeiteten einzelnen Nachrichten genau einmal empfangen werden. Der Absender wird dann über den Zustellfehler benachrichtigt. Wenn der `durable`-Wert `false` ist, wird dieses Attribut ignoriert, und es werden Nachrichten ohne Zustellungszusicherung übertragen. Die Standardeinstellung ist `true`. Weitere Informationen finden Sie unter <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.|  
|`maxBufferPoolSize`|Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt. Der Standard ist 8.|  
|`maxReceivedMessageSize`|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Byte einschließlich Header angibt, die von dieser Bindung verarbeitet wird. Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standard ist 65536. Auf diese Weise sollen Denial-of-Service-Angriffe (DoS) reduziert werden.|  
|`maxRetryCycles`|Eine ganze Zahl, die die Anzahl der Wiederholungszyklen für die Funktion zur Erkennung nicht verarbeitbarer Nachrichten angibt. Eine Nachricht gilt als nicht verarbeitbare Nachricht, wenn alle erneuten Zustellversuche fehlgeschlagen sind. Der Standard ist 3. Weitere Informationen finden Sie unter <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.|  
|`name`|Erforderliches Attribut. Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`QueueTransferProtocol`|Ein gültiger <xref:System.ServiceModel.QueueTransferProtocol>-Wert, der den Wartenschlangentransport für den Kommunikationskanal angibt, der von dieser Bindung verwendet wird. MSMQ unterstützt keine Active Directory-Adressierung in Verbindung mit dem SOAP Reliable Messaging Protocol. Aus diesem Grund sollten Sie dieses Attribut nicht festgelegt, um `Srmp` oder `Srmps` bei der `u``seActiveDirectory` -Attributsatz zur `true`.|  
|`receiveErrorHandling`|Ein <xref:System.ServiceModel.ReceiveErrorHandling>-Wert, der angibt, wie nicht verarbeitbare und nicht zustellbare Nachrichten behandelt werden.|  
|`receiveRetryCount`|Eine ganze Zahl, die die maximalen Versuche angibt, die dem Warteschlangen-Manager zum Senden einer Nachricht zur Verfügung stehen, bevor diese in die Wiederholungswarteschlange übertragen wird.|  
|`receiveTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|  
|`retryCycleDelay`|Ein TimeSpan-Wert, der die Zeitverzögerung zwischen den Wiederholungszyklen angibt, wenn versucht wird, eine Nachricht zuzustellen, die nicht sofort zugestellt werden konnte. Der Wert definiert nur die Mindestwartezeit, da die tatsächliche Wartezeit länger sein kann. Der Standardwert ist 00:10:00. Weitere Informationen finden Sie unter <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.|  
|`sendTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`timeToLive`|Ein TimeSpan-Wert, der angibt, wie lange die Nachricht gültig ist, bis sie abläuft und in die Warteschlange für unzustellbare Nachrichten übertragen wird. Der Standardwert ist 1.00:00:00.<br /><br /> Dieses Attribut wird festgelegt, um sicherzustellen, dass zeitkritische Nachrichten nicht veralten, bevor sie von den empfangenden Anwendungen verarbeitet werden. Eine Nachricht in einer Warteschlange, die nicht von der empfangenden Anmeldung innerhalb des angegebenen Zeitintervalls verarbeitet wird, läuft ab. Abgelaufene Nachrichten werden an eine besondere Warteschlange gesendet: die Warteschlange für unzustellbare Nachrichten. Der Speicherort der Warteschlange für unzustellbare Meldungen wird mithilfe des `DeadLetterQueue`-Attributs festgelegt. Andernfalls gilt die entsprechende, auf den Zusicherungen basierende Standardeinstellung.|  
|`usingActiveDirectory`|Gibt einen booleschen Wert zurück, der angibt, ob Warteschlangenadressen mit Active Directory konvertiert werden sollen.<br /><br /> MSMQ-Warteschlangenadressen können aus Pfadnamen oder aus direkten Formatnamen bestehen. Bei direkten Formatnamen wird der Computername von MSMQ mit DNS, NetBIOS oder IP aufgelöst. Bei Pfadnamen wird der Computername von MSMQ mit Active Directory aufgelöst.<br /><br /> Der URI einer Nachrichtenwarteschlange wird vom [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Wartenschlangentransport standardmäßig in einen direkten Formatnamen konvertiert. Durch Festlegen der `UseActiveDirectory`-Eigenschaft auf True kann von einer Anwendung angegeben werden, dass der Computername vom Warteschlangentransport mit Active Directory anstelle von DNS, NetBIOS oder IP aufgelöst werden soll.|  
|`useMsmqTracing`|Ein boolescher Wert, der angibt, ob von dieser Bindung verarbeitete Nachrichten verfolgt werden sollen. Die Standardeinstellung ist `false`. Wenn die Ablaufverfolgung aktiviert ist, werden Berichtsnachrichten erstellt und jedes Mal an die Berichtswarteschlange gesendet, wenn die Nachricht einen Computer mit Message Queuing erreicht oder verlässt.|  
|`useSourceJournal`|Ein boolescher Wert, der angibt, ob Kopien der von dieser Bindung verarbeiteten Nachrichten in der Quelljournalwarteschlange gespeichert werden sollen. Die Standardeinstellung ist `false`.<br /><br /> Anwendungen in Warteschlangen, die Nachrichten aufzeichnen möchten, die die Ausgangswarteschlange des Computers verlassen haben, können die Nachrichten in eine Journalwarteschlange kopieren. Wenn eine Nachricht die Ausgangswarteschlange verlässt und eine Bestätigung empfangen wird, dass die Nachricht auf dem Zielcomputer empfangen wurde, wird eine Kopie der Nachricht in der Systemjournalwarteschlange des sendenden Computers beibehalten.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ReaderQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Bindungen >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `netMsmqBinding`-Bindung stellt Unterstützung für Warteschlangen bereit, indem MSMQ (Microsoft Message Queuing) als Transport eingesetzt wird, und ermöglicht Unterstützung für lose miteinander verknüpfte Anwendungen, Fehlerisolierung, Lastenausgleich und Vorgänge im Offlinemodus. Eine Erörterung dieser Features finden Sie unter [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## <a name="example"></a>Beispiel  
  
```xml  
<configuration>  
<system.ServiceModel>  
    <bindings>  
           <netMsmqBinding>  
                <binding   
                         closeTimeout="00:00:10"   
                         openTimeout="00:00:20"   
                         receiveTimeout="00:00:30"  
                         sendTimeout="00:00:40"  
                         deadLetterQueue="net.msmq://localhost/blah"   
                         durable="true"   
                         exactlyOnce="true"   
                         maxReceivedMessageSize="1000"  
                         maxRetries="11"  
                         maxRetryCycles="12"   
                         poisonMessageHandling="Disabled"   
                         rejectAfterLastRetry="false"   
                         retryCycleDelay="00:05:55"   
                         timeToLive="00:11:11"   
                         sourceJournal="true"  
                         useMsmqTracing="true"  
                         useActiveDirectory="true">  
                         <security>  
                             <message clientCredentialType="Windows" />  
                         </security>  
            </netMsmqBinding>  
    </bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>  
 [\<Binden von >](../../../../../docs/framework/misc/binding.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [Warteschlangen in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
