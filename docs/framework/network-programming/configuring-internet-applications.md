---
title: Konfigurieren von Internetanwendungen
description: Informationen zur Verwendung des Elements <system.Net> zum Konfigurieren von Internetanwendungen im .NET Framework Dieser Artikel enthält Beispielcode.
ms.date: 03/30/2017
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
ms.openlocfilehash: 796752ebf6e3cc5c3dac2a20213934f35d31b392
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287461"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="ac450-104">Konfigurieren von Internetanwendungen</span><span class="sxs-lookup"><span data-stu-id="ac450-104">Configuring Internet Applications</span></span>

<span data-ttu-id="ac450-105">Das Konfigurationselement [\<system.Net> (Netzwerkeinstellungen)](../configure-apps/file-schema/network/system-net-element-network-settings.md) enthält Informationen zur Netzwerkkonfiguration von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ac450-105">The [\<system.Net> Element (Network Settings)](../configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="ac450-106">Mit dem Element [\<system.Net> (Netzwerkeinstellungen)](../configure-apps/file-schema/network/system-net-element-network-settings.md) können Sie Proxyserver und Parameter zur Verbindungsverwaltung festlegen sowie benutzerdefinierte Authentifizierungs- und Anforderungsmodule in Ihre Anwendung einfügen.</span><span class="sxs-lookup"><span data-stu-id="ac450-106">Using the [\<system.Net> Element (Network Settings)](../configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="ac450-107">Mit dem Element [\<defaultProxy> (Netzwerkeinstellungen)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) wird der Proxyserver definiert, der von der Klasse `GlobalProxySelection` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ac450-107">The [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="ac450-108">Der Standardproxy wird von jeder <xref:System.Net.HttpWebRequest> verwendet, die über keine eigene auf einen bestimmten Wert festgelegte <xref:System.Net.HttpWebRequest.Proxy%2A>-Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="ac450-108">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="ac450-109">Zusätzlich zum Festlegen der Proxyadresse können Sie eine Liste mit Serveradressen erstellen, die den Proxy nicht verwenden. Sie können auch angeben, dass der Proxy nicht für lokale Adressen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac450-109">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="ac450-110">Beachten Sie, dass die Microsoft Internet Explorer-Einstellungen mit den Konfigurationseinstellungen kombiniert werden, wobei letztere Vorrang haben.</span><span class="sxs-lookup"><span data-stu-id="ac450-110">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="ac450-111">Im folgenden Beispiel wird die Standard-Proxyserveradresse auf `http://proxyserver` festgelegt. Es wird angegeben, dass der Proxy nicht für lokale Adressen verwendet werden soll und dass alle Anforderungen an Server, die sich in der Domäne „contoso.com“ befinden, den Proxy umgehen sollen.</span><span class="sxs-lookup"><span data-stu-id="ac450-111">The following example sets the default proxy server address to `http://proxyserver`, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
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
  
 <span data-ttu-id="ac450-112">Verwenden Sie das Element [\<connectionManagement> (Netzwerkeinstellungen)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md), um die Anzahl von permanenten Verbindungen zu konfigurieren, die mit einem bestimmten Server oder mit allen anderen Servern hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="ac450-112">Use the [\<connectionManagement> Element (Network Settings)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="ac450-113">Im folgenden Beispiel wird die Anwendung so konfiguriert, dass zwei permanente Verbindungen mit dem Server `www.contoso.com`, vier permanente Verbindungen mit dem Server mit der IP-Adresse 192.168.1.2 und eine permanente Verbindung mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac450-113">The following example configures the application to use two persistent connections to the server `www.contoso.com`, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
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
  
 <span data-ttu-id="ac450-114">Benutzerdefinierte Authentifizierungsmodule werden mit dem Element [\<authenticationModules> (Netzwerkeinstellungen)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ac450-114">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="ac450-115">Benutzerdefinierte Authentifizierungsmodule müssen die Schnittstelle <xref:System.Net.IAuthenticationModule> implementieren.</span><span class="sxs-lookup"><span data-stu-id="ac450-115">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="ac450-116">Im folgenden Beispiel wird ein benutzerdefiniertes Authentifizierungsmodul konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ac450-116">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="ac450-117">Mit dem Element [\<webRequestModules> (Netzwerkeinstellungen)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) können Sie die Anwendung so konfigurieren, dass benutzerdefinierte protokollspezifische Module zum Anfordern von Informationen von Internetressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ac450-117">You can use the [\<webRequestModules> Element (Network Settings)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="ac450-118">Die jeweiligen Module müssen die Schnittstelle <xref:System.Net.IWebRequestCreate> implementieren.</span><span class="sxs-lookup"><span data-stu-id="ac450-118">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="ac450-119">Sie können die Standardanforderungsmodule „HTTP“, „HTTPS“ und „file“ überschreiben, indem Sie wie im folgenden Beispiel gezeigt Ihr Standardmodul in der Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="ac450-119">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac450-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac450-120">See also</span></span>

- [<span data-ttu-id="ac450-121">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ac450-121">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="ac450-122">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ac450-122">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="ac450-123">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ac450-123">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
