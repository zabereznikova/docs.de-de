---
title: Proxykonfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b543097d0fc85c502bd36f22225958f9239ccd71
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="proxy-configuration"></a>Proxykonfiguration
Ein Proxyserver verarbeitet Clientanforderungen für Ressourcen. Ein Proxy kann eine angeforderte Ressource aus dem Cache zurückgeben oder die Anforderung an den Server weiterleiten, auf dem sich die Ressource befindet. Proxys können die Netzwerkleistung durch Reduzierung der Anzahl der an Remote-Server gesendeten Anforderungen verbessern. Proxys können auch verwendet werden, um den Zugriff auf Ressourcen einzuschränken.  
  
## <a name="adaptive-proxies"></a>Adaptive Proxys  
 Im .NET Framework gibt es zwei Grundtypen von Proxys: adaptive und statische. Adaptive Proxys ändern Sie ihre Einstellungen, wenn sich die Konfiguration ändert. Wenn z. B. ein Laptop-Benutzer eine DFÜ-Netzwerkverbindung gestartet hat, würde ein adaptiver Proxy diese Änderung erkennen, das neue Konfigurationsskript entdecken und ausführen und die Einstellungen entsprechend anpassen.  
  
 Adaptive Proxys werden durch ein Konfigurationsskript konfiguriert (siehe [Automatische Proxyerkennung](../../../docs/framework/network-programming/automatic-proxy-detection.md)). Das Skript generiert eine Reihe von Anwendungsprotokollen und ein Proxy für jedes Protokoll.  
  
 Mehrere Optionen steuern, wie das Skript ausgeführt wird. Sie können Folgendes angeben:  
  
-   Wie oft wird ist das Konfigurationsskript heruntergeladen und ausgeführt?  
  
-   Wie lange gilt es zu warten, bis das Skript heruntergeladen werden kann.  
  
-   Welche Anmeldeinformationen Ihr System verwenden sollte, um auf den den Proxy zuzugreifen.  
  
-   Welche Anmeldeinformationen Ihr System zum Downloaden des Konfigurationsskripts verwenden sollte.  
  
 Änderungen in der Netzwerkumgebung erfordern, dass das System einen neuen Satz von Proxys verwendet. Wenn eine Netzwerkverbindung ausfällt oder eine neue Netzwerkverbindung initialisiert wird, muss das System die entsprechende Quelle des Konfigurationsskripts in der neuen Umgebung erkennen und das neue Skript ausführen.  
  
 Die folgende Tabelle zeigt die Konfigurationsoptionen für einen adaptiven Proxy.  
  
|Attribut-, Eigenschafts- oder Konfigurationseinstellung|Beschreibung|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|Verstrichene Zeit in Sekunden zwischen den Script-Downloads.|  
|`scriptDownloadTimeout`|Wartezeit (in Sekunden) für das Skript-Download.|  
|`useDefaultCredentials` oder <xref:System.Net.WebProxy.UseDefaultCredentials>|Steuert, ob das System die Standardanmeldeinformationen verwendet, um auf einen Proxy zugreifen.|  
|`useDefaultCredentialForScriptDownload`|Steuert, ob das System die Standardanmeldeinformationen verwendet, um das Skript herunterladen.|  
|`usesystemdefaults`|Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte. Wenn dieser Wert auf "True" gesetzt wird, dann werden die statischen Proxy-Einstellungen von Internet Explorer verwendet.<br /><br /> Wenn dieser Wert "false" lautet oder nicht gesetzt wird, dann können die statischen Proxy-Einstellungen in der Konfiguration angegeben werden und die Internet Explorer-Proxy-Einstellungen werden überschrieben. Dieser Wert muss auch auf "false" gesetzt oder darf nicht festgelegt werden, damit adaptive Proxys aktiviert werden.|  
  
 Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a>Statische Proxys  
 Statische Proxys werden in der Regel explizit von einer Anwendung konfiguriert, oder wenn eine Konfigurationsdatei von einer Anwendung oder vom System aufgerufen wird. Statische Proxys sind in Netzwerken nützlich, in denen die Topologie sich nur selten verändert, wie z. B. bei einem Desktop-Computer, der mit einem Unternehmensnetzwerk verbunden ist.  
  
 Mehrere Optionen steuern, wie ein statischer Proxy arbeitet. Sie können Folgendes angeben:  
  
-   Die Proxy-Adresse.  
  
-   Gibt an, ob der Proxy für lokale Adressen umgangen werden soll.  
  
-   Gibt an, ob der Proxy für eine Gruppe von Adressen umgangen werden soll.  
  
 Die folgende Tabelle zeigt die Konfigurationsoptionen für einen statischen Proxy.  
  
|Attribut-, Eigenschafts- oder Konfigurationseinstellung|Beschreibung|  
|--------------------------------------------------------|-----------------|  
|`proxyaddress` oder <xref:System.Net.WebProxy.Address>|Die Adresse des Proxyservers, der verwendet werden soll.|  
|`bypassonlocal` oder <xref:System.Net.WebProxy.BypassProxyOnLocal>|Steuert, ob der Proxy für lokale Adressen umgangen wird.|  
|`bypasslist` oder <xref:System.Net.WebProxy.BypassArrayList>|Beschreibt mit regulären Ausdrücken eine Reihe von Adressen, die den Proxyserver umgehen.|  
|`usesystemdefaults`|Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte. Wenn dieser Wert auf "True" gesetzt wird, dann werden die statischen Proxy-Einstellungen von Internet Explorer verwendet. Wen auf dem .NET Framework 2.0 dieser Wert auf "True" festgelegt wird, werden die Internet Explorer-Proxy-Einstellungen nicht von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben. Auf dem .NET Framework 1.1 können die Internet Explorer-Proxy-Einstellungen von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben werden.<br /><br /> Wenn dieser Wert "false" lautet oder nicht gesetzt wird, dann können die statischen Proxy-Einstellungen in der Konfiguration angegeben werden und die Internet Explorer-Proxy-Einstellungen werden überschrieben. Dieser Wert muss auch auf "false" gesetzt oder darf nicht festgelegt werden, damit adaptive Proxys aktiviert werden.|  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [Automatische Proxyerkennung](../../../docs/framework/network-programming/automatic-proxy-detection.md)
