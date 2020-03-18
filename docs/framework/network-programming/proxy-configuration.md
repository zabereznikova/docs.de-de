---
title: Proxykonfiguration
ms.date: 06/18/2018
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
ms.openlocfilehash: 1fbfe25b90e810ff96924a2341582ff3f5ee5e5d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047354"
---
# <a name="proxy-configuration"></a>Proxykonfiguration
Ein Proxyserver verarbeitet Clientanforderungen für Ressourcen. Ein Proxy kann eine angeforderte Ressource aus dem Cache zurückgeben oder die Anforderung an den Server weiterleiten, auf dem sich die Ressource befindet. Proxys können die Netzwerkleistung durch Reduzierung der Anzahl der an Remote-Server gesendeten Anforderungen verbessern. Proxys können auch verwendet werden, um den Zugriff auf Ressourcen einzuschränken.  
  
## <a name="adaptive-proxies"></a>Adaptive Proxys  
 Im .NET Framework gibt es zwei Grundtypen von Proxys: adaptive und statische. Adaptive Proxys ändern Sie ihre Einstellungen, wenn sich die Konfiguration ändert. Wenn z. B. ein Laptop-Benutzer eine DFÜ-Netzwerkverbindung gestartet hat, würde ein adaptiver Proxy diese Änderung erkennen, das neue Konfigurationsskript entdecken und ausführen und die Einstellungen entsprechend anpassen.  
  
 Adaptive Proxys werden durch ein Konfigurationsskript konfiguriert (siehe [Automatische Proxyerkennung](automatic-proxy-detection.md)). Das Skript generiert eine Reihe von Anwendungsprotokollen und ein Proxy für jedes Protokoll.  
  
 Änderungen in der Netzwerkumgebung erfordern, dass das System einen neuen Satz von Proxys verwendet. Wenn eine Netzwerkverbindung ausfällt oder eine neue Netzwerkverbindung initialisiert wird, muss das System die entsprechende Quelle des Konfigurationsskripts in der neuen Umgebung erkennen und das neue Skript ausführen.  
  
 Sie können das Attribut `usesystemdefault` des Elements [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) in der Konfigurationsdatei verwenden. Das `usesystemdefault`-Attribut steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Proxyumgehungsliste und lokale Proxyumgehung) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollten. Wenn dieser Wert auf `true` festgelegt wird, werden die statischen Proxyeinstellungen von Internet Explorer verwendet. Wenn der Wert auf `false` oder gar nicht festgelegt ist, können die statischen Proxyeinstellungen in der Konfiguration angegeben werden. Sie überschreiben dann die Proxyeinstellungen von Internet Explorer. Dieser Wert muss auch auf `false` oder gar nicht festgelegt werden, damit adaptive Proxys aktiviert werden.  
  
 Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a>Statische Proxys  
 Statische Proxys werden in der Regel explizit von einer Anwendung konfiguriert, oder wenn eine Konfigurationsdatei von einer Anwendung oder vom System aufgerufen wird. Statische Proxys sind in Netzwerken nützlich, in denen die Topologie sich nur selten verändert, wie z. B. bei einem Desktop-Computer, der mit einem Unternehmensnetzwerk verbunden ist.  
  
 Mehrere Optionen steuern, wie ein statischer Proxy arbeitet. Sie können Folgendes angeben:  
  
- Die Proxy-Adresse.  
  
- Gibt an, ob der Proxy für lokale Adressen umgangen werden soll.  
  
- Gibt an, ob der Proxy für eine Gruppe von Adressen umgangen werden soll.  
  
 Die folgende Tabelle zeigt die Konfigurationsoptionen für einen statischen Proxy.  
  
|Attribut-, Eigenschafts- oder Konfigurationseinstellung|Beschreibung|  
|--------------------------------------------------------|-----------------|  
|`proxyaddress` oder <xref:System.Net.WebProxy.Address>|Die Adresse des Proxyservers, der verwendet werden soll.|  
|`bypassonlocal` oder <xref:System.Net.WebProxy.BypassProxyOnLocal>|Steuert, ob der Proxy für lokale Adressen umgangen wird.|  
|`bypasslist` oder <xref:System.Net.WebProxy.BypassArrayList>|Beschreibt mit regulären Ausdrücken eine Reihe von Adressen, die den Proxyserver umgehen.|  
|`usesystemdefault`|Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte. Wenn dieser Wert auf `true` festgelegt wird, werden die statischen Proxyeinstellungen von Internet Explorer verwendet. Wenn dieser Wert in .NET Framework 2.0 auf `true` festgelegt wird, werden die Proxyeinstellungen von Internet Explorer nicht von anderen Proxyeinstellungen in der Konfigurationsdatei überschrieben. Auf dem .NET Framework 1.1 können die Internet Explorer-Proxy-Einstellungen von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben werden.<br /><br /> Wenn dieser Wert auf `false` oder gar nicht festgelegt wird, können die statischen Proxyeinstellungen in der Konfiguration angegeben werden. Sie überschreiben dann die Proxyeinstellungen von Internet Explorer. Dieser Wert muss auch auf `false` oder gar nicht festgelegt werden, damit adaptive Proxys aktiviert werden.|  
  
 Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [Automatische Proxyerkennung](automatic-proxy-detection.md)
