---
title: "Konfigurieren von Internetanwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Downloaden von Internetressourcen, Standardproxy"
  - "Senden von Daten, Standardproxy"
  - "Empfangen von Daten, Standardproxy"
  - "Downloaden von Internetressourcen, Konfigurieren von Internetanwendungen"
  - "Protokollspezifische Module"
  - "Benutzerdefinierte Authentifizierungsmodule"
  - "Empfangen von Daten, Konfigurieren von Internetanwendungen"
  - "Konfigurationseinstellungen [.NET Framework], Internetanwendungen"
  - "Anfordern von Daten aus dem Internet, Konfigurieren von Internetanwendungen"
  - "Anfordern von Daten aus dem Internet, Standardproxy"
  - "Antwort auf Internetanforderung, Standardproxy"
  - "Internet, Konfigurieren von Internetanwendungen"
  - "Antwort auf Internetanforderung, Konfigurieren von Internetanwendungen"
  - "Standardproxy"
  - "Netzwerkressourcen, Standardproxy"
  - "Senden von Daten, Konfigurieren von Internetanwendungen"
  - "Netzwerkressourcen, Konfigurieren von Internetanwendungen"
  - "Internet, Standardproxy"
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Konfigurieren von Internetanwendungen
Das [\<system.Net\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) Konfigurationselement enthält Netzwerkkonfigurationsinformationen für Anwendungen.  Mit dem [\<system.Net\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)\-Elements können Sie Proxyserver festlegen, legen Module der Verbindungsverwaltungs\-Parameter und benutzerdefinierte der Authentifizierung und der Anforderung des Include in der Anwendung.  
  
 Das [\<defaultProxy\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)\-Element definiert den Proxyserver, der von der `GlobalProxySelection`\-Klasse zurückgegeben wird.  Jedes <xref:System.Net.HttpWebRequest>, der einen eigenen <xref:System.Net.HttpWebRequest.Proxy%2A>\-Eigenschaft nicht auf einen bestimmten Wert verfügt, verwendet den Standardproxy.  Zusätzlich zum Festlegen der Proxyadresse, können Sie eine Liste von Serveradressen erstellen, die nicht den Proxy verwenden, und Sie können angeben, dass der Proxy für lokale Adressen nicht verwendet werden sollte.  
  
 Beachten Sie unbedingt, dass Microsoft Internet Explorer\-Einstellungen mit den Konfigurationseinstellungen kombiniert werden, mit der letzten nehmenden Rangfolge.  
  
 Im folgenden Beispiel wird die standardmäßige Proxyserveradresse zu http:\/\/proxyserver, angibt, dass der Proxy für lokale Adressen nicht verwendet werden sollte, fest und angibt, dass alle Anforderungen den Servern in der Domäne contoso.com\- den Proxy umgehen möchten.  
  
```  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 Verwenden Sie das [\<connectionManagement\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)\-Element, um die Anzahl von beständigen Verbindungen zu konfigurieren, die auf einem bestimmten Server oder zu allen anderen Servern hergestellt werden können.  Im folgenden Beispiel wird die Anwendung so konfiguriert, zwei persistente Verbindungen mit dem Server www.contoso.com, vier dauerhafte Verbindungen mit dem Server mit der IP\-Adresse 192.168.1.2 und eine dauerhafte Verbindung zu allen anderen Servern zu verwenden.  
  
```  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 Benutzerdefinierte Authentifizierungsmodule werden mit dem [\<authenticationModules\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)\-Element konfiguriert.  Benutzerdefinierte Authentifizierungsmodule müssen die <xref:System.Net.IAuthenticationModule>\-Schnittstelle implementieren.  
  
 Im folgenden Beispiel konfiguriert ein benutzerdefiniertes Authentifizierungsmodul.  
  
```  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 Sie können das [\<webRequestModules\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)\-Element verwenden, um die Anwendung zu konfigurieren, benutzerdefinierte protokollspezifische Module zu verwenden, um Informationen aus den Internetressourcen anzufordern.  Die angegebenen Module müssen die <xref:System.Net.IWebRequestCreate>\-Schnittstelle implementieren.  Sie können die Standardeinstellung HTTP, HTTPS\- und Dateianforderungsmodule überschreiben, indem Sie das benutzerdefinierte Modul in der Konfigurationsdatei angeben, wie im folgenden Beispiel gezeigt.  
  
```  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## Siehe auch  
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Netzwerkeinstellungsschema](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<system.Net\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)