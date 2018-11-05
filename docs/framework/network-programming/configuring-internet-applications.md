---
title: Konfigurieren von Internetanwendungen
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
ms.openlocfilehash: bdc63064d3f0d809c196e77a890ba697f9d4deea
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197235"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="290f2-102">Konfigurieren von Internetanwendungen</span><span class="sxs-lookup"><span data-stu-id="290f2-102">Configuring Internet Applications</span></span>
<span data-ttu-id="290f2-103">Das Konfigurationselement [\<system.Net> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) enthält Informationen zur Netzwerkkonfiguration von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="290f2-103">The [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="290f2-104">Mit dem Element [\<system.Net> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) können Sie Proxyserver und Parameter zur Verbindungsverwaltung festlegen sowie benutzerdefinierte Authentifizierung und Anforderungsmodule in Ihre Anwendung einfügen.</span><span class="sxs-lookup"><span data-stu-id="290f2-104">Using the [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="290f2-105">Mit dem Element [\<defaultProxy> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) wird der Proxyserver definiert, der von der Klasse `GlobalProxySelection` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="290f2-105">The [\<defaultProxy> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="290f2-106">Der Standardproxy wird von jeder <xref:System.Net.HttpWebRequest> verwendet, die über keine eigene auf einen bestimmten Wert festgelegte <xref:System.Net.HttpWebRequest.Proxy%2A>-Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="290f2-106">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="290f2-107">Zusätzlich zum Festlegen der Proxyadresse können Sie eine Liste mit Serveradressen erstellen, die den Proxy nicht verwenden. Sie können auch angeben, dass der Proxy nicht für lokale Adressen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="290f2-107">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="290f2-108">Beachten Sie, dass die Microsoft Internet Explorer-Einstellungen mit den Konfigurationseinstellungen kombiniert werden, wobei letztere Vorrang haben.</span><span class="sxs-lookup"><span data-stu-id="290f2-108">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="290f2-109">Im folgenden Beispiel wird die Standard-Proxyserveradresse auf `http://proxyserver` festgelegt. Es wird angegeben, dass der Proxy nicht für lokale Adressen verwendet werden soll und dass alle Anforderungen an Server, die sich in der Domäne „contoso.com“ befinden, den Proxy umgehen sollen.</span><span class="sxs-lookup"><span data-stu-id="290f2-109">The following example sets the default proxy server address to `http://proxyserver`, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
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
  
 <span data-ttu-id="290f2-110">Verwenden Sie das Element [\<connectionManagement> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md), um die Anzahl von permanenten Verbindungen, die mit einem bestimmten Server oder mit allen anderen Servern hergestellt werden können, zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="290f2-110">Use the [\<connectionManagement> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="290f2-111">Im folgenden Beispiel wird die Anwendung so konfiguriert, dass zwei permanente Verbindungen mit dem Server `www.contoso.com`, vier permanente Verbindungen mit dem Server mit der IP-Adresse 192.168.1.2 und eine permanente Verbindung mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="290f2-111">The following example configures the application to use two persistent connections to the server `www.contoso.com`, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
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
  
 <span data-ttu-id="290f2-112">Benutzerdefinierte Authentifizierungsmodule werden mit dem Element [\<authenticationModules> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="290f2-112">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="290f2-113">Benutzerdefinierte Authentifizierungsmodule müssen die Schnittstelle <xref:System.Net.IAuthenticationModule> implementieren.</span><span class="sxs-lookup"><span data-stu-id="290f2-113">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="290f2-114">Im folgenden Beispiel wird ein benutzerdefiniertes Authentifizierungsmodul konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="290f2-114">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="290f2-115">Mit dem Element [\<webRequestModules> (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) können Sie die Anwendung so konfigurieren, dass benutzerdefinierte protokollspezifische Module zum Anfordern von Informationen von Internetressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="290f2-115">You can use the [\<webRequestModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="290f2-116">Die jeweiligen Module müssen die Schnittstelle <xref:System.Net.IWebRequestCreate> implementieren.</span><span class="sxs-lookup"><span data-stu-id="290f2-116">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="290f2-117">Sie können die Standardanforderungsmodule „HTTP“, „HTTPS“ und „file“ überschreiben, indem Sie wie im folgenden Beispiel gezeigt Ihr Standardmodul in der Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="290f2-117">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="290f2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="290f2-118">See Also</span></span>  
 [<span data-ttu-id="290f2-119">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="290f2-119">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="290f2-120">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="290f2-120">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="290f2-121">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="290f2-121">\<system.Net> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)
