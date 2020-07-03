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
# <a name="automatic-proxy-detection"></a>Automatische Proxyerkennung
Automatische Proxyerkennung ist ein Prozess, mit dem ein Webproxyserver vom System identifiziert und zum Senden von Anforderungen im Auftrag des Clients verwendet wird. Diese Funktion ist auch bekannt als Web Proxy Auto-Discovery (WPAD). Wenn die automatische Proxyerkennung aktiviert ist, versucht das System, ein Proxykonfigurationsskript zu finden, das für die Rückgabe des Proxysatzes verantwortlich ist, der für die Anforderung verwendet werden kann. Wenn das Proxykonfigurationsskript gefunden wird, wird es heruntergeladen, kompiliert und auf dem lokalen Computer ausgeführt, wenn Proxyinformationen, der Anforderungsstream oder die Antwort für eine Anforderung abgerufen werden, die eine <xref:System.Net.WebProxy>-Instanz verwendet.  
  
 Automatische Proxyerkennung erfolgt durch die <xref:System.Net.WebProxy>-Klasse und kann die Einstellungen auf Anforderungsebene und in Konfigurationsdateien und Einstellungen verwenden, die das Internet Explorer-Dialogfeld **Local Area Network (LAN)** verwenden.  
  
> [!NOTE]
> Sie können das Internet Explorer-Dialogfeld **Local Area Network (LAN)-Einstellungen** anzeigen, indem Sie **Tools** aus dem Internet Explorer-Hauptmenü und anschließend **Internetoptionen** auswählen. Klicken Sie anschließend auf der Registerkarte **Verbindungen** auf **LAN-Einstellungen**.  
  
 Wenn die automatische Proxyerkennung aktiviert ist, versucht die <xref:System.Net.WebProxy>-Klasse das Proxykonfigurationsskript wie folgt zu finden:  
  
1. Der Funktion WinINet `InternetQueryOption` wird verwendet, um das zuletzt vom Internet Explorer erkannte Proxykonfigurationsskript zu suchen.  
  
2. Wenn das Skript nicht gefunden wurde, verwendet die <xref:System.Net.WebProxy>-Klasse das Dynamic Host Configuration Protocol (DHCP), um das Skript zu suchen. Der DHCP-Server kann entweder mit dem Speicherort (Hostname) des Skripts oder mit der vollständigen URL für das Skript antworten.  
  
3. Wenn DHCP den WPAD-Host nicht identifiziert, wird DNS für einen Host mit WPAD als Namen oder Alias abgefragt.  
  
4. Wenn der Host nicht identifiziert wird und der Speicherort eines Proxykonfigurationsskripts durch die Internet Explorer-LAN-Einstellungen oder eine Konfigurationsdatei angegeben ist, wird dieser Speicherort verwendet.  
  
> [!NOTE]
> Anwendungen, die als NT-Dienst oder als Teil von ASP.NET ausgeführt werden, verwenden die Internet Explorer-Proxyeinstellungen (falls vorhanden) des aufrufenden Benutzers. Diese Einstellungen sind möglicherweise nicht für alle Dienstanwendungen verfügbar.  
  
 Proxys werden pro Benutzeroberfläche konfiguriert. Eine Benutzeroberfläche ist ein Element im Netzwerkverbindungsdialogfeld und kann ein physisches Netzwerkgerät (Modem oder Ethernet-Karte) oder eine virtuelle Schnittstelle (z.B. eine über ein Netzwerkgerät ausgeführte VPN-Verbindung) sein. Wenn sich eine Benutzeroberfläche ändert (z.B. ändert eine Funkverbindung einen Zugriffspunkt oder ein VPN wird aktiviert), wird der Proxyerkennungsalgorithmus erneut ausgeführt.  
  
 Die Proxyeinstellungen werden standardmäßig von Internet Explorer verwendet, um den Proxy zu erkennen. Wenn Ihre Anwendung unter einem nicht interaktiven Konto (ohne eine einfache Möglichkeit zum Konfigurieren von Proxyeinstellungen für Internet Explorer) ausgeführt wird, oder wenn Sie Proxyeinstellungen verwenden möchten, die sich von den Internet Explorer-Einstellungen unterscheiden, können Sie den Proxy konfigurieren, indem Sie eine Konfigurationsdatei mit dem [\<defaultProxy>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) und dem [\<proxy>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/proxy-element-network-settings.md) definieren.  
  
 Für Anforderungen, die Sie erstellen, können Sie automatische Proxyerkennung auf der Anforderungsebene deaktivieren, indem ein NULL-<xref:System.Net.WebRequest.Proxy%2A> mit Ihrer Anforderung verwendet wird. Dies wird im folgenden Codebeispiel gezeigt.  
  
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
  
 Anforderungen, die keinen Proxy haben, verwenden den Standardproxy Ihrer Anwendungsdomäne, der in der <xref:System.Net.WebRequest.DefaultWebProxy%2A>-Eigenschaft verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [\<system.Net>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/system-net-element-network-settings.md)
