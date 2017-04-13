---
title: "&lt;wsHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "wsHttpBinding-Element"
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# &lt;wsHttpBinding&gt;
Definiert eine sichere, zuverlässige und interoperable Bindung für Nicht\-Duplexdienstverträge dar.  Die Bindung implementiert die folgenden Spezifikationen: WS\-Reliable Messaging für Zuverlässigkeit und WS\-Security für Nachrichtensicherheit und Authentifizierung.  Für den Transport wird HTTP verwendet und für die Nachrichtencodierung Text\/XML\-Codierung.  
  
## Syntax  
  
```  
  
<wsHttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
                textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
        <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string" />  
          <message   
             algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                          clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
             establishSecurityContext="Boolean"  
             negotiateServiceCredential="Boolean" />  
        </security>  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"   
            maxNameTableCharCount="Integer"           
            maxStringContentLength="Integer" />  
    </binding>  
</wsHttpBinding>  
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
|maxReceivedMessageSize|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header angibt, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist.  Der Absender einer Nachricht, die diese Grenze überschreitet, erhält einen SOAP\-Fehler.  Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.  Der Standard ist 65536.|  
|messageEncoding|Definiert den Encoder, der verwendet wird, um die SOAP\-Nachricht zu codieren.  Folgende Werte sind gültig:<br /><br /> -   Text: Verwenden Sie einen Textnachrichtenencoder.<br />-   Mtom: Verwendung eines MTOM\-Encoders \(Message Transmission Organisation Mechanism 1.0\).<br />-   Der Standardwert ist Text.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.|  
|Name|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.  Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.  Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.  Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhalten finden Sie unter [Vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|proxyAddress|Ein URI, der die Adresse des HTTP\-Proxys angibt.  Wenn `useSystemWebProxy` `true` ist, muss diese Einstellung `null` lauten.  Die Standardeinstellung ist `null`.|  
|receiveTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|sendTimeout|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|textEncoding|Gibt die Zeichensatzcodierung an, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll.  Folgende Werte sind gültig:<br /><br /> -   UnicodeFffeTextEncoding: Unicode BigEndian\-Codierung.<br />-   Utf16TextEncoding: 16\-Bit\-Codierung.<br />-   Utf8TextEncoding: 8\-Bit\-Codierung.<br /><br /> Der Standardwert ist Utf8TextEncoding.<br /><br /> Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|  
|transactionFlow|Ein boolescher Wert, der angibt, ob die Bindung geleitete WS\-Transaktionen unterstützt.  Die Standardeinstellung ist `false`.|  
|useDefaultWebProxy|Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP\-Proxy des Systems verwendet wird.  Die Standardeinstellung ist `true`.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|Definiert die Beschränkungen der Komplexität von SOAP\-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden.  Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[reliableSession](http://msdn.microsoft.com/de-de/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|Gibt an, ob zuverlässige Sitzungen zwischen Kanalendpunkten aufgebaut werden.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindungen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## Hinweise  
 Die `WSHttpBinding` ist der `BasicHttpBinding` ähnlich, stellt jedoch mehr Webdienstfunktionen bereit.  Sie verwendet wie BasicHttpBinding den HTTP\-Transport und stellt Nachrichtensicherheit bereit, bietet jedoch darüber hinaus Transaktionen, zuverlässiges Messaging und WS\-Adressierung, entweder standardmäßig aktiviert oder über ein einziges Steuerelement verfügbar.  
  
## Beispiel  
  
```  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://foo/bar"  
                    textEncoding="utf-16"  
                    useDefaultWebProxy="false">  
                    <reliableSession ordered="false"  
                         inactivityTimeout="00:02:00"  
                         enabled="true" />  
                    <security mode="Transport">  
                         <transport clientCredentialType="Digest"  
                            proxyCredentialType="None"  
                            realm="someRealm" />  
                         <message clientCredentialType="Windows"  
                            negotiateServiceCredential="false"  
                            algorithmSuite="Aes128"   
                            defaultProtectionLevel="None" />  
                    </security>  
                </binding>  
           </wsHttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.WSHttpBinding>   
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement>   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)