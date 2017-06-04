---
title: "&lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 84179d77-825d-44b9-895a-ab08e7aa044d
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;webHttpBinding&gt;
Definiert ein Bindungselement, das zum Konfigurieren von Endpunkten für [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Webdienste verwendet wird, die auf HTTP\-Anforderungen und nicht auf SOAP\-Nachrichten reagieren.  
  
## Syntax  
  
```  
  
<webHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxBufferSize="integer"  
        maxReceivedMessageSize="Integer"  
        name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
        useDefaultWebProxy="Boolean">  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        <security mode="None/Transport/TransportCredentialOnly">  
            <transport clientCredentialType =   
                 "Basic/Certificate/Digest/None/Ntlm/Windows"  
                  proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                  realm="string" />  
        </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</webHttpBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|allowCookies|Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert.  Der Standardwert ist false.<br /><br /> Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX\-Webdiensten interagieren, die Cookies verwenden.  Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.|  
|bypassProxyOnLocal|Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll.  Die Standardeinstellung ist `false`.|  
|closeTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|hostnameComparisonMode|Gibt den HTTP\-Hostnamen\-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostnameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird.  Der Standardwert lautet <xref:System.ServiceModel.HostnameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.|  
|maxBufferPoolSize|Eine ganze Zahl, die die maximale Pufferpoolgröße für diese Bindung angibt.  Der Standardwert ist 524.288 Byte \(512 \* 1024\).  Viele Teile von Windows Communication Foundation \(WCF\) verwenden Puffer.  Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.  Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.  So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.|  
|maxBufferSize|Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen.  Der Standardwert ist 524.288 \(0x80000\) Bytes.|  
|maxReceivedMessageSize|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.  Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen Fehler.  Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.  Der Standard ist 65536. **Note:**  Es reicht im ASP.NET\-Kompatibilitätsmodus nicht aus, nur diesen Wert zu erhöhen.  Sie sollten auch den Wert von `httpRuntime` erhöhen \(siehe [httpRuntime\-Element \(ASP.NET\-Einstellungsschema\)](http://msdn.microsoft.com/de-de/e9b81350-8aaf-47cc-9843-5f7d0c59f369)\).|  
|Name|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.  Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.  Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.  Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhalten finden Sie unter [Vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|proxyAddress|Ein URI, der die Adresse des HTTP\-Proxys angibt.  Wenn `useSystemWebProxy` `true` ist, muss diese Einstellung `null` lauten.  Die Standardeinstellung ist `null`.|  
|receiveTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|sendTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|transferMode.|Ein <xref:System.ServiceModel.TransferMode>\-Wert, der angibt, ob der mit der Bindung konfigurierte Dienst Streaming\- oder Puffermodi \(oder beides\) für die Nachrichtenübertragung einsetzt.  Die Standardeinstellung ist `Buffered`.|  
|useDefaultWebProxy|Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP\-Proxy des Systems verwendet wird.  Die Standardeinstellung ist `true`.|  
|writeEncoding|Gibt die Zeichenkodierung an, die für den Nachrichtentext verwendet wird.  Folgende Werte sind gültig:<br /><br /> UnicodeFffeTextEncoding: Unicode BigEndian\-Codierung.<br /><br /> Utf16TextEncoding: 16\-Bit\-Codierung.<br /><br /> Utf8TextEncoding: 8\-Bit\-Codierung.<br /><br /> Der Standardwert ist Utf8TextEncoding.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Definiert die Beschränkungen der Komplexität von POX\-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WebHttpSecurityElement>.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindungen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## Hinweise  
 Das [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Webprogrammiermodell ermöglicht es Entwicklern, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Webdienste über HTTP\-Anforderungen verfügbar zu machen, die POX\-Messaging anstatt von SOAP\-basiertem Messaging verwenden.  Damit Clients mit einem Dienst über HTTP\-Anforderungen kommunizieren können, muss ein Endpunkt des Diensts mit der [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) konfiguriert sein, an die \<WebHttpBehavior\> angefügt ist.  
  
 Die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Unterstützung für Syndication und ASP.AJAX\-Integration ist über dem Webprogrammiermodell implementiert.  Weitere Informationen zum Modell finden Sie unter [WCF\-Web\-HTTP\-Programmiermodell](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.WebHttpBinding>   
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>   
 [WCF\-Web\-HTTP\-Programmiermodell](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)