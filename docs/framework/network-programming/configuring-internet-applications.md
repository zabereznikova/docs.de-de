---
title: Konfigurieren von Internetanwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
caps.latest.revision: 15
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a4a013b8a4ff60222bb88c6e9c4f14badd689b5d
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="configuring-internet-applications"></a>Konfigurieren von Internetanwendungen
Das Konfigurationselement [\<system.Net> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) enthält Informationen zur Netzwerkkonfiguration von Anwendungen. Mit dem Element [\<system.Net> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) können Sie Proxyserver und Parameter zur Verbindungsverwaltung festlegen sowie benutzerdefinierte Authentifizierung und Anforderungsmodule in Ihre Anwendung einfügen.  
  
 Mit dem Element [\<defaultProxy> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) wird der Proxyserver definiert, der von der Klasse `GlobalProxySelection` zurückgegeben wird. Der Standardproxy wird von jeder <xref:System.Net.HttpWebRequest> verwendet, die über keine eigene auf einen bestimmten Wert festgelegte <xref:System.Net.HttpWebRequest.Proxy%2A>-Eigenschaft verfügt. Zusätzlich zum Festlegen der Proxyadresse können Sie eine Liste mit Serveradressen erstellen, die den Proxy nicht verwenden. Sie können auch angeben, dass der Proxy nicht für lokale Adressen verwendet werden soll.  
  
 Beachten Sie, dass die Microsoft Internet Explorer-Einstellungen mit den Konfigurationseinstellungen kombiniert werden, wobei letztere Vorrang haben.  
  
 Im folgenden Beispiel wird die Standard-Proxyserveradresse auf „http://proxyserver“ festgelegt. Es wird angegeben, dass der Proxy nicht für lokale Adressen verwendet werden soll und dass alle Anforderungen an Server, die sich in der Domäne „contoso.com“ befinden, den Proxy umgehen sollen.  
  
```xml  
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
  
 Verwenden Sie das Element [\<connectionManagement> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md), um die Anzahl von permanenten Verbindungen, die mit einem bestimmten Server oder mit allen anderen Servern hergestellt werden können, zu konfigurieren. Im folgenden Beispiel wird die Anwendung so konfiguriert, dass zwei permanente Verbindungen mit dem Server www.contoso.com, vier permanente Verbindungen mit dem Server mit der IP-Adresse 192.168.1.2 und eine permanente Verbindung mit allen anderen Servern verwendet werden.  
  
```xml  
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
  
 Benutzerdefinierte Authentifizierungsmodule werden mit dem Element [\<authenticationModules> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) konfiguriert. Benutzerdefinierte Authentifizierungsmodule müssen die Schnittstelle <xref:System.Net.IAuthenticationModule> implementieren.  
  
 Im folgenden Beispiel wird ein benutzerdefiniertes Authentifizierungsmodul konfiguriert.  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 Mit dem Element [\<webRequestModules> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) können Sie die Anwendung so konfigurieren, dass benutzerdefinierte protokollspezifische Module zum Anfordern von Informationen von Internetressourcen verwendet werden. Die jeweiligen Module müssen die Schnittstelle <xref:System.Net.IWebRequestCreate> implementieren. Sie können die Standardanforderungsmodule „HTTP“, „HTTPS“ und „file“ überschreiben, indem Sie wie im folgenden Beispiel gezeigt Ihr Standardmodul in der Konfigurationsdatei angeben.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 [Network Programming in the .NET Framework (Netzwerkprogrammierung in .NET Framework)](../../../docs/framework/network-programming/index.md)   
 [Network Settings Schema (Netzwerkeinstellungsschema)](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<system.Net>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)

