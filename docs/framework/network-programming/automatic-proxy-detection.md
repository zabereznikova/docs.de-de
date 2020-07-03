---
title: Automatische Proxyerkennung
description: Hier erfahren Sie mehr über die automatische Proxyerkennung, bei der das System einen Webproxyserver identifiziert und zum Senden von Anforderungen im Auftrag des Clients verwendet.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
ms.openlocfilehash: dbd5d7fa671ae5ec3b7dc00205f0c9d8381bb3ce
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502695"
---
# <a name="automatic-proxy-detection"></a><span data-ttu-id="c7e7c-103">Automatische Proxyerkennung</span><span class="sxs-lookup"><span data-stu-id="c7e7c-103">Automatic Proxy Detection</span></span>
<span data-ttu-id="c7e7c-104">Automatische Proxyerkennung ist ein Prozess, mit dem ein Webproxyserver vom System identifiziert und zum Senden von Anforderungen im Auftrag des Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-104">Automatic proxy detection is a process by which a Web proxy server is identified by the system and used to send requests on behalf of the client.</span></span> <span data-ttu-id="c7e7c-105">Diese Funktion ist auch bekannt als Web Proxy Auto-Discovery (WPAD).</span><span class="sxs-lookup"><span data-stu-id="c7e7c-105">This feature is also known as Web Proxy Auto-Discovery (WPAD).</span></span> <span data-ttu-id="c7e7c-106">Wenn die automatische Proxyerkennung aktiviert ist, versucht das System, ein Proxykonfigurationsskript zu finden, das für die Rückgabe des Proxysatzes verantwortlich ist, der für die Anforderung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-106">When automatic proxy detection is enabled, the system attempts to locate a proxy configuration script that is responsible for returning the set of proxies that can be used for the request.</span></span> <span data-ttu-id="c7e7c-107">Wenn das Proxykonfigurationsskript gefunden wird, wird es heruntergeladen, kompiliert und auf dem lokalen Computer ausgeführt, wenn Proxyinformationen, der Anforderungsstream oder die Antwort für eine Anforderung abgerufen werden, die eine <xref:System.Net.WebProxy>-Instanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-107">If the proxy configuration script is found, the script is downloaded, compiled, and run on the local computer when proxy information, the request stream, or the response is obtained for a request that uses a <xref:System.Net.WebProxy> instance.</span></span>  
  
 <span data-ttu-id="c7e7c-108">Automatische Proxyerkennung erfolgt durch die <xref:System.Net.WebProxy>-Klasse und kann die Einstellungen auf Anforderungsebene und in Konfigurationsdateien und Einstellungen verwenden, die das Internet Explorer-Dialogfeld **Local Area Network (LAN)** verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-108">Automatic proxy detection is performed by the <xref:System.Net.WebProxy> class and can employ request-level settings, settings in configuration files, and settings specified using the Internet Explorer **Local Area Network (LAN)** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7e7c-109">Sie können das Internet Explorer-Dialogfeld **Local Area Network (LAN)-Einstellungen** anzeigen, indem Sie **Tools** aus dem Internet Explorer-Hauptmenü und anschließend **Internetoptionen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-109">You can display the Internet Explorer **Local Area Network (LAN) Settings** dialog box by selecting **Tools** from the Internet Explorer main menu and then selecting **Internet Options**.</span></span> <span data-ttu-id="c7e7c-110">Klicken Sie anschließend auf der Registerkarte **Verbindungen** auf **LAN-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-110">Next, select the **Connections** tab, and click **LAN Settings**.</span></span>  
  
 <span data-ttu-id="c7e7c-111">Wenn die automatische Proxyerkennung aktiviert ist, versucht die <xref:System.Net.WebProxy>-Klasse das Proxykonfigurationsskript wie folgt zu finden:</span><span class="sxs-lookup"><span data-stu-id="c7e7c-111">When automatic proxy detection is enabled, the <xref:System.Net.WebProxy> class attempts to locate the proxy configuration script as follows:</span></span>  
  
1. <span data-ttu-id="c7e7c-112">Der Funktion WinINet `InternetQueryOption` wird verwendet, um das zuletzt vom Internet Explorer erkannte Proxykonfigurationsskript zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-112">The WinINet `InternetQueryOption` function is used to locate the proxy configuration script most recently detected by Internet Explorer.</span></span>  
  
2. <span data-ttu-id="c7e7c-113">Wenn das Skript nicht gefunden wurde, verwendet die <xref:System.Net.WebProxy>-Klasse das Dynamic Host Configuration Protocol (DHCP), um das Skript zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-113">If the script is not located, the <xref:System.Net.WebProxy> class uses the Dynamic Host Configuration Protocol (DHCP) to locate the script.</span></span> <span data-ttu-id="c7e7c-114">Der DHCP-Server kann entweder mit dem Speicherort (Hostname) des Skripts oder mit der vollständigen URL für das Skript antworten.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-114">The DHCP server can respond either with the location (host name) of the script or with the full URL for the script.</span></span>  
  
3. <span data-ttu-id="c7e7c-115">Wenn DHCP den WPAD-Host nicht identifiziert, wird DNS für einen Host mit WPAD als Namen oder Alias abgefragt.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-115">If DHCP does not identify the WPAD host, DNS is queried for a host with WPAD as its name or alias.</span></span>  
  
4. <span data-ttu-id="c7e7c-116">Wenn der Host nicht identifiziert wird und der Speicherort eines Proxykonfigurationsskripts durch die Internet Explorer-LAN-Einstellungen oder eine Konfigurationsdatei angegeben ist, wird dieser Speicherort verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-116">If the host is not identified and the location of a proxy configuration script is specified by the Internet Explorer LAN settings or a configuration file, this location is used.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7e7c-117">Anwendungen, die als NT-Dienst oder als Teil von ASP.NET ausgeführt werden, verwenden die Internet Explorer-Proxyeinstellungen (falls vorhanden) des aufrufenden Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-117">Applications running as an NT Service or as part of ASP.NET use the Internet Explorer proxy server settings (if available) of the invoking user.</span></span> <span data-ttu-id="c7e7c-118">Diese Einstellungen sind möglicherweise nicht für alle Dienstanwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-118">These settings may not be available for all service applications.</span></span>  
  
 <span data-ttu-id="c7e7c-119">Proxys werden pro Benutzeroberfläche konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-119">Proxies are configured on a per-connectoid basis.</span></span> <span data-ttu-id="c7e7c-120">Eine Benutzeroberfläche ist ein Element im Netzwerkverbindungsdialogfeld und kann ein physisches Netzwerkgerät (Modem oder Ethernet-Karte) oder eine virtuelle Schnittstelle (z.B. eine über ein Netzwerkgerät ausgeführte VPN-Verbindung) sein.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-120">A connectoid is an item in the network connection dialog, and can be a physical network device (a modem or Ethernet card) or a virtual interface (such as a VPN connection running over a network device).</span></span> <span data-ttu-id="c7e7c-121">Wenn sich eine Benutzeroberfläche ändert (z.B. ändert eine Funkverbindung einen Zugriffspunkt oder ein VPN wird aktiviert), wird der Proxyerkennungsalgorithmus erneut ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-121">When a connectoid changes (for example, a wireless connection changes an access point, or a VPN is enabled), the proxy detection algorithm is run again.</span></span>  
  
 <span data-ttu-id="c7e7c-122">Die Proxyeinstellungen werden standardmäßig von Internet Explorer verwendet, um den Proxy zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-122">By default, the Internet Explorer proxy settings are used to detect the proxy.</span></span> <span data-ttu-id="c7e7c-123">Wenn Ihre Anwendung unter einem nicht interaktiven Konto (ohne eine einfache Möglichkeit zum Konfigurieren von Proxyeinstellungen für Internet Explorer) ausgeführt wird, oder wenn Sie Proxyeinstellungen verwenden möchten, die sich von den Internet Explorer-Einstellungen unterscheiden, können Sie den Proxy konfigurieren, indem Sie eine Konfigurationsdatei mit dem [\<defaultProxy>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) und dem [\<proxy>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/proxy-element-network-settings.md) definieren.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-123">If your application is running under a non-interactive account (without a convenient way to configure IE proxy settings), or if you want to use proxy settings different than the IE settings, you can configure your proxy by creating a configuration file with the [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) and [\<proxy> Element (Network Settings)](../configure-apps/file-schema/network/proxy-element-network-settings.md) elements defined.</span></span>  
  
 <span data-ttu-id="c7e7c-124">Für Anforderungen, die Sie erstellen, können Sie automatische Proxyerkennung auf der Anforderungsebene deaktivieren, indem ein NULL-<xref:System.Net.WebRequest.Proxy%2A> mit Ihrer Anforderung verwendet wird. Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-124">For requests that you create, you can disable automatic proxy detection at the request level by using a null <xref:System.Net.WebRequest.Proxy%2A> with your request, as shown in the following code example.</span></span>  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub
```  
  
 <span data-ttu-id="c7e7c-125">Anforderungen, die keinen Proxy haben, verwenden den Standardproxy Ihrer Anwendungsdomäne, der in der <xref:System.Net.WebRequest.DefaultWebProxy%2A>-Eigenschaft verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c7e7c-125">Requests that do not have a proxy use your application domain's default proxy, which is available in the <xref:System.Net.WebRequest.DefaultWebProxy%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e7c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7e7c-126">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="c7e7c-127">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c7e7c-127">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
