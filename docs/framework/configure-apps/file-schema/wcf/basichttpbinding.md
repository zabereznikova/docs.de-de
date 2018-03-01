---
title: '&lt;basicHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- basicHttpBinding Element
ms.assetid: 85cf1a4f-26c2-48c7-bda6-6c960d5d3fb3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80494dd0050c7a3a873e6885a8001a55171ffc8e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltbasichttpbindinggt"></a>&lt;basicHttpBinding&gt;
Stellt eine Bindung dar, die ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst zum Konfigurieren und Verfügbarmachen von Endpunkten verwenden kann, die mit ASMX-basierten Webdiensten und -Clients und anderen mit WS-I Basic Profile 1.1 konformen Diensten kommunizieren können.  
  
 \<system.ServiceModel>  
\<bindings>  
\<basicHttpBinding>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<basicHttpBinding>  
   <binding   
       allowCookies="Boolean"  
       bypassProxyOnLocal="Boolean"  
       closeTimeout="TimeSpan"   
       envelopeVersion="None/Soap11/Soap12"  
       hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"  
       maxReceivedMessageSize="Integer"  
       messageEncoding="Text/Mtom"  
              name="string"   
       openTimeout="TimeSpan"   
       proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
              textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
       useDefaultWebProxy="Boolean"  
       <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">  
           <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"  
                  proxyCredentialType="None/Basic/Digest/Ntlm/Windows"  
                                    realm="string" />  
           <message   
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                            clientCredentialType="UserName/Certificate"/>  
       </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`allowCookies`|Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert. Die Standardeinstellung ist `false`.<br /><br /> Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden. Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.|  
|`bypassProxyOnLocal`|Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll. Die Standardeinstellung ist `false`.<br /><br /> Eine Internetressource gilt als lokal, wenn sie über eine lokale Adresse verfügt. Eine lokale Adresse befindet sich auf dem gleichen Computer, im LAN oder Intranet und kann anhand des fehlenden Punkts (.) erkannt werden, wie bei den URIs "http://webserver/" und "http://localhost/".<br /><br /> Durch dieses Attribut wird festgelegt, ob mit BasicHttpBinding konfigurierte Endpunkte den Proxyserver zum Zugreifen auf lokale Ressourcen verwenden. Wenn dieses Attribut `true` ist, wird bei Anforderungen lokaler Internetressourcen der Proxyserver nicht verwendet. Ist dieses Attribut auf `true` festgelegt, sollten Sie den Hostnamen anstatt localhost verwenden, wenn die Clients bei der Kommunikation mit Diensten auf demselben Computer einen Proxy nutzen sollen.<br /><br /> Wenn dieses Attribut `false` ist, werden alle Internetanforderungen über den Proxyserver ausgeführt.|  
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`envelopeVersion`|Gibt die SOAP-Version an, die für Nachrichten verwendet wird, die von dieser Bindung verarbeitet werden. Der einzig gültige Wert ist Soap11.|  
|`hostnameComparisonMode`|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird. Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.|  
|`maxBufferPoolSize`|Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen. Der Standardwert ist 524288 (0x80000) Bytes.<br /><br /> Der Puffer-Manager reduziert den Pufferaufwand durch Verwendung eines Pufferpools. Puffer sind zur Verarbeitung von Nachrichten durch den Dienst erforderlich, wenn sie aus dem Kanal eintreffen. Wenn die Speicherkapazität des Pufferpools zur Verarbeitung der Nachrichten nicht ausreicht, muss der Puffer-Manager zusätzliche Speicherkapazität aus dem CLR-Heap zuweisen. Dadurch wird die Auslastung der Garbage Collection erhöht. Eine umfangreiche Zuweisung aus dem CLR-Heap der Garbage Collection weist darauf hin, dass die Größe des Pufferpools nicht ausreichend ist und dass die Leistung durch eine größere Zuweisung infolge einer Erhöhung der des maximalen Grenzwerts, der durch dieses Attribut angegeben wird, verbessert werden kann.|  
|`maxBufferSize`|Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden. Der Standardwert ist 65.536 Bytes.|  
|`maxReceivedMessageSize`|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist. Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standardwert beträgt 65.536 Bytes.|  
|`messageEncoding`|Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren. Folgende Werte sind gültig:<br /><br /> -Text: Verwenden Sie einen textnachrichtenencoder.<br />-Mtom: Verwendung eines Encoders Message Transmission Organisation Mechanism 1.0 (MTOM).<br /><br /> Der Standardwert ist Text. Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.|  
|`name`|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren. Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`namespace`|Gibt den XML-Namespace der Bindung an. Der Standardwert ist "http://tempuri.org/Bindings". Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.|  
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`proxyAddress`|Ein URI, der die Adresse des HTTP-Proxys enthält. Wenn `useSystemWebProxy` auf `true` festgelegt ist, muss diese Einstellung `null` lauten. Die Standardeinstellung ist `null`.|  
|`receiveTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|  
|`sendTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`textEncoding`|Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> -BigEndianUnicode: Unicode BigEndian-Codierung.<br />– Unicode: 16-Bit-Codierung.<br />-UTF8: 8-Bit-Codierung<br /><br /> Der Standard ist UTF8. Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|  
|`transferMode`|Ein gültiger <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.|  
|`useDefaultWebProxy`|Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems bei Verfügbarkeit verwendet werden soll. Die Standardeinstellung ist `true`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.|  
|[\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## <a name="remarks"></a>Hinweise  
 BasicHttpBinding verwendet HTTP als Transportprotokoll für das Senden von SOAP 1.1-Nachrichten. Ein Dienst kann diese Bindung zum Verfügbarmachen von mit WS-I BP 1.1 konformen Endpunkten verwenden, wie z.&#160;B. Endpunkte für ASMX-Clients. In ähnlicher Weise kann ein Client BasicHttpBinding zum Kommunizieren mit Diensten verwenden, die mit WS-I BP 1.1 konforme Endpunkte verfügbar machen, wie z.&#160;B. ASMX-Webdienste oder mit BasicHttpBinding konfigurierte Dienste.  
  
 Sicherheit ist standardmäßig deaktiviert, jedoch können hinzugefügt werden, Festlegen der Mode-Attribut der [ \<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) einen anderen Wert als untergeordnetes Element `None`. Standardmäßig wird "Text"-Nachrichtencodierung und UTF-8-Textcodierung verwendet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung von <xref:System.ServiceModel.BasicHttpBinding> veranschaulicht, bei der HTTP-Kommunikation und maximale Interoperabilität mit Webdiensten der ersten und zweiten Generation sichergestellt wird. Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben. Der Bindungstyp wird im `binding`-Attribut des `<endpoint>`-Elements angegeben. Wenn Sie die Standardbindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren. Der Endpunkt muss auf die Bindungskonfiguration anhand des Namens und des `bindingConfiguration`-Attributs des `<endpoint>`-Elements verweisen, wie im folgenden Konfigurationscode für den Dienst gezeigt.  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="basicHttpBinding"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <basicHttpBinding>  
        <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Text"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="example"></a>Beispiel  
 Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Die Funktionalität aus dem vorherigen Beispiel kann erreicht werden, indem bindingConfiguration aus der Endpunktadresse und der Name aus der Bindung entfernt wird.  
  
```xml  
<system.serviceModel>   
  <services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="basicHttpBinding"  
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
     <basicHttpBinding>  
        <binding   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxReceivedMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Text"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
              <security mode="None" />  
         </binding>  
     </basicHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Weitere Informationen zur Standardkonfiguration und namenlos Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
