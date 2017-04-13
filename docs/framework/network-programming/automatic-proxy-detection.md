---
title: "Automatische Proxyerkennung | Microsoft Docs"
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
  - "Automatische Proxyerkennungen"
  - "Web Proxy Auto-Discovery"
  - "Webproxy"
  - "Automatisches Erkennen von Proxys"
  - "WebProxy-Klasse, Automatische Proxyerkennungen"
  - "Proxys, Automatische Erkennung"
  - "Netzwerk"
  - "WPAD (Web Proxy Auto-Discovery)"
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Automatische Proxyerkennung
Automatische Proxyerkennung ist ein Prozess, durch den ein Internet\-Proxyserver vom System identifiziert und wird verwendet, um Anforderungen im Namen des Clients zu senden.  Dieses Feature wird auch als WAPD \(Web Proxy Auto\-Discovery\) bezeichnet.  Wenn automatisch, wird Proxyerkennung, die System versucht, ein Proxykonfigurationsskript zu suchen können, das für die Rückgabe des Satzes der Proxy zuständig ist, die für die Anforderung verwendet werden können.  Wenn das Proxykonfigurationsskript gefunden wird, wird das Skript heruntergeladen, kompiliert und auf dem lokalen Computer, wenn Proxyinformationen, der Anforderungsstream oder die Antwort auf eine Anforderung abgerufen wird, die eine <xref:System.Net.WebProxy>\-Instanz verwendet.  
  
 Automatische Proxyerkennung wird durch die <xref:System.Net.WebProxy>\-Klasse ausgeführt und kann AnforderungEbene Einstellungen, Einstellungen in den Konfigurationsdateien und Einstellungen einfügen, die mithilfe des Dialogfelds Internet Explorer **LAN** angegeben werden.  
  
> [!NOTE]
>  Sie können das Dialogfeld Internet Explorer **Einstellungen für lokales Netzwerk** anzeigen, indem Sie **Tools** aus dem Internet Explorer\-Hauptmenü auswählen und dann **Internetoptionen** auswählen.  dann, wählen Sie die Registerkarte **Verbindungen** aus, und klicken Sie auf **LAN\-Einstellungen**.  
  
 Wenn automatisch, wird Proxyerkennung, die <xref:System.Net.WebProxy>\-Klassenversuche, das Proxykonfigurationsskript zu suchen können, wie folgt:  
  
1.  Die Funktion WinInets `InternetQueryOption` wird verwendet, um das Proxykonfigurationsskript zuletzt zu suchen, die von Internet Explorer erkannt wird.  
  
2.  Wenn das Skript nicht gefunden wird, verwendet die <xref:System.Net.WebProxy>\-Klasse das Dynamic Host Configuration\-Protokoll \(DHCP\) das Skript zu suchen.  Der DHCP\-Server kann entweder mit dem Speicherort \(Hostname\) des Skripts oder mit dem vollständigen URL für das Skript reagieren.  
  
3.  Wenn DHCP nicht den WPAD\-Host angibt, wird DNS für einen Host mit WPAD als Name oder Alias abgefragt.  
  
4.  Wenn der Host nicht identifiziert werden und Position eines Proxykonfigurationsskripts durch die Internet Explorer\-LANeinstellungen oder eine Konfigurationsdatei angegeben wird, wird dieser Speicherort verwendet.  
  
> [!NOTE]
>  Die Anwendungen, die als NT ausgeführt werden, halten aus oder als Teil ASP.NET verwenden die Internet Explorer\-Proxyservereinstellungen \(sofern verfügbar\) des aufrufenden Benutzers.  Diese Einstellungen sind möglicherweise nicht für alle Dienstanwendungen verfügbar.  
  
 Proxy werden auf einem pro\-connectoid Basis konfiguriert.  Ein connectoid ist ein Element im Netzwerkverbindungsdialogfeld und kann ein physisches Netzwerkgerät \(ein Modem oder eine Ethernetkarte\) oder eine virtuelle Schnittstelle sein \(wie eine VPN\-Verbindung, die über ein Netzwerkgerät ausgeführt wird\).  Wenn ein connectoid ändert \(beispielsweise, ändert eine Funkverbindung Verbindung einen Zugriffspunkt, oder ein VPN ist aktiviert\), wird der Proxyerkennungsalgorithmus erneut ausgeführt.  
  
 Standardmäßig werden die Internet Explorer\-Proxyeinstellungen verwendet, um den Proxy zu erkennen.  Wenn die Anwendung unter einem Konto allein stehendes \(ohne eine praktische Möglichkeit, IE\-Proxyeinstellungen konfigurieren\) ausgeführt wird oder wenn Sie die Proxyeinstellungen verwenden möchten, die als IE\-Einstellungen unterschiedlich sind, können Sie den Proxy konfigurieren, indem Sie eine Konfigurationsdatei den definierten [\<defaultProxy\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) und [\<proxy\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)\-Elementen erstellen.  
  
 Für Anforderungen, die Sie erstellen, können Sie die automatische Proxyerkennung auf Anforderung deaktivieren, indem Sie NULL <xref:System.Net.WebRequest.Proxy%2A> mit der Anforderung, wie im folgenden Codebeispiel gezeigt glätten, verwenden.  
  
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
  
 Anforderungen, die nicht der Standardproxy einer des Proxys Verwendung der Anwendungsdomäne verfügen, der in der <xref:System.Net.WebRequest.DefaultWebProxy%2A>\-Eigenschaft verfügbar ist.  
  
## Siehe auch  
 <xref:System.Net.WebProxy>   
 <xref:System.Net.WebRequest>   
 [\<system.Net\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)