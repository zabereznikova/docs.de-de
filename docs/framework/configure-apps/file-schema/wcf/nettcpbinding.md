---
title: <netTcpBinding>
description: Stellt eine sichere, zuverlässige und optimierte Bindung dar, die nur für die Computer übergreifende WCF-Kommunikation mit TCP vorgesehen ist. Zuverlässiges Messaging ist standardmäßig deaktiviert.
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: a366b26d87c8796822e4fbbb2001823c116f2629
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556127"
---
# \<netTcpBinding>

Gibt eine sichere, zuverlässige und optimierte Bindung an, die computerübergreifende Kommunikation unterstützt. Diese Bindung generiert standardmäßig einen Laufzeitkommunikationsstapel mit Windows-Sicherheit für die Nachrichtensicherheit und die Authentifizierung, TCP für die Nachrichtenübermittlung sowie binäre Nachrichtencodierung.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`hostNameComparisonMode`|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird. Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.|  
|`listenBacklog`|Eine positive ganze Zahl, die die maximale Anzahl an Kanälen angibt, die im Listener darauf warten, akzeptiert zu werden. Verbindungen oberhalb des Limits werden in die Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird. Das `connectionTimeout`-Attribut beschränkt die Zeit, die ein Client wartet, bevor eine Verbindungsausnahme ausgelöst wird. Der Standardwert ist 10.|  
|`maxBufferPoolSize`|Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt. Der Standardwert ist 512 * 1024 Bytes. Viele Teile von Windows Communication Foundation (WCF) verwenden Puffer. Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer. Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen. So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.|  
|`maxBufferSize`|Eine positive ganze Zahl, die die maximale Größe des Puffers in Bytes angibt, der zum Speichern von Nachrichten verwendet wird.<br /><br /> Wenn das `transferMode`-Attribut auf `Buffered` festgelegt ist, sollte dieses Attribut auf den `maxReceivedMessageSize`-Attributwert festgelegt werden.<br /><br /> Wenn das `transferMode`-Attribut auf `Streamed` festgelegt ist, darf dieses Attribut den `maxReceivedMessageSize`-Attributwert nicht überschreiten und sollte mindestens auf die Größe des Headers festgelegt werden.<br /><br /> Der Standard ist 65536. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|`maxConnections`|Eine ganze Zahl, die die maximale Anzahl ausgehender und eingehender Verbindungen angibt, die der Dienst erstellt bzw. akzeptiert. Eingehende und ausgehende Verbindungen werden mit einem separaten, von diesem Attribut angegebenen Grenzwert verglichen.<br /><br /> Eingehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.<br /><br /> Ausgehende Verbindungen, die diesen Grenzwert überschreiten, werden in die Warteschlange gestellt, bis wieder Speicherplatz verfügbar wird.<br /><br /> Der Standardwert ist 10.|  
|`maxReceivedMessageSize`|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist. Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP-Fehler. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standard ist 65536.|  
|`name`|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`portSharingEnabled`|Ein boolescher Wert, der angibt, ob die TCP-Anschlussfreigabe für diese Verbindung aktiviert ist. Wenn dies `false` ist, verwendet jede Bindung ihren eigenen Anschluss. Diese Einstellung ist nur für Dienste relevant, da Clients nicht betroffen sind.|  
|`receiveTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|  
|`sendTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`transactionFlow`|Ein boolescher Wert, der angibt, ob die Bindung geleitete WS-Transaktionen unterstützt. Der Standardwert ist `false`.|  
|`transactionProtocol`|Gibt das Transaktionsprotokoll an, das mit dieser Bindung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> Der Standardwert ist OleTransactions. Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.|  
|`transferMode`|Ein <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## <a name="remarks"></a>Hinweise

Diese Bindung generiert standardmäßig eine Laufzeitkommunikation, die Transportsicherheit, TCP zur Nachrichtenübermittlung und eine binäre Nachrichtencodierung verwendet. Diese Bindung ist eine geeignete von einem System bereitgestellte Windows Communication Foundation (WCF) für die Kommunikation über ein Intranet.  
  
 Die Standardkonfiguration für `netTcpBinding` ist schneller als die von bereitgestellte Konfiguration `wsHttpBinding` , Sie ist jedoch nur für die WCF-Kommunikation vorgesehen. Das Sicherheitsverhalten ist mit dem optionalen `securityMode`-Attribut konfigurierbar. Die Verwendung von WS-ReliableMessaging ist mit dem optionalen `reliableSessionEnabled`-Attribut konfigurierbar. Zuverlässiges Messaging ist jedoch standardmäßig deaktiviert. Die vom System bereitgestellten HTTP-Bindungen, wie z.&#160;B. `wsHttpBinding` und `basicHttpBinding`, sind im Allgemeinen so konfiguriert, dass Funktionen standardmäßig aktiviert werden ,während die `netTcpBinding`-Bindung Funktionen standardmäßig deaktiviert, sodass Sie die Unterstützung für eine der WS-*-Spezifikationen explizit übernehmen müssen. Das bedeutet, dass die Standardkonfiguration für TCP Meldungen zwischen Endpunkten schneller austauscht als die standardmäßig für die HTTP-Bindungen festgelegten Konfigurationen.  
  
## <a name="example"></a>Beispiel

Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben. Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben. Wenn Sie die netTcpBinding-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren. Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`-Attributs verweisen. Im folgenden Beispiel wird eine Bindungskonfiguration definiert.  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
