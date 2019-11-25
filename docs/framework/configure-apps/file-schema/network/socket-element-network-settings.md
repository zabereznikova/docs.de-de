---
title: <socket>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089092"
---
# <a name="socket-element-network-settings"></a>\<Socket >-Element (Netzwerkeinstellungen)
Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Einstellungen**](settings-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Socket >**

## <a name="syntax"></a>Syntax  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|**Attribut**|**Beschreibung**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Gibt an, ob der Socket immer Beendigungs Anschlüsse für Accept-Methodenaufrufe verwenden soll. Der Standardwert ist `false`sein.|  
|`alwaysUseCompletionPortsForConnect`|Gibt an, ob der Socket immer Beendigungs Anschlüsse für Verbindungsmethoden Aufrufe verwenden soll. Der Standardwert ist `false`sein.|  
|`ipProtectionLevel`|Gibt die Standard <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> an, die für einen Socket verwendet werden sollen. Der Standardwert hängt von der Windows-Version ab.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Einstellungen](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Die Attribute `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` werden verwendet, um das Standardverhalten in Bezug auf die Verwendung von Abschlussports durch die Klassen im <xref:System.Net.Sockets?displayProperty=nameWithType>. Namespace anzugeben. Abschlussports werden für hochleistungsfähige Server Anwendungen empfohlen.  
  
 Der Standardwert für die Attribute `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` ist **false**.  
  
 Der <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForAccept` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten. Der <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForConnect` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
 Das `ipProtectionLevel`-Attribut gibt die Standard <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> an, die für einen Socket verwendet werden sollen. Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>-Eigenschaft ermöglicht die Konfiguration einer Einschränkung für einen IPv6-Socket zu einem angegebenen Bereich, z. b. Adressen mit demselben Link lokalen oder Standort lokalen Präfix. Mit dieser Option können Anwendungen Zugriffs Einschränkungen für IPv6-Sockets platzieren. Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen. Mit dieser Option wird der Bereich eines Abhör Sockets erweitert oder eingeschränkt, bei Bedarf der uneingeschränkte Zugriff von öffentlichen und privaten Benutzern ermöglicht oder der Zugriff auf dieselbe Website eingeschränkt.  
  
 Diese `ipProtectionLevel` Attribut Einstellung betrifft nur den ersten eingehenden Datenverkehr:  
  
- Ein TCP-Server, der eingehende Verbindungen für einen Socket überwacht.  
  
- Eine UDP-Anwendung, die ein Paket für einen Socket empfängt.  
  
 Diese Konfigurationseinstellung wirkt sich nicht auf bereits festgelegte TCP-Verbindungen aus (Datenverkehr ist in beiden Richtungen uneingeschränkt) und wirkt sich nicht auf eine Anwendung aus, die UDP-Pakete sendet.  
  
 Die möglichen Werte für die `ipProtectionLevel`-Attribut Einstellung entsprechen den definierten, in der <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>-Enumeration angegebenen Schutz Ebenen wie folgt:  
  
|**Attribut Wert**|**Beschreibung**|  
|-|-|  
|Edgerestrihiert|Die IP-Schutz Ebene ist Edge-eingeschränkt. Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind. Diese Einstellung lässt die NAT-Überquerung (Network Address Translation) nicht zu, da die Teredo-Implementierung von Windows verwendet wird. Diese Anwendungen können IPv4-Firewalls umgehen, sodass Anwendungen gegen Internet Angriffe auf den geöffneten Port festgeschrieben werden müssen. Unter Windows Server 2003 und Windows XP ist Edge restricted der Standardwert für die IP-Schutz Ebene für einen Socket.|  
|Eingeschränkter Zugriff|Die IP-Schutz Ebene ist eingeschränkt. Dieser Wert wird von Intranetanwendungen verwendet, die keine Internet Szenarios implementieren. Diese Anwendungen werden in der Regel nicht getestet oder gegen Angriffe im Internet untersucht. Mit dieser Einstellung wird der empfangene Datenverkehr nur auf Link-Local beschränkt.|  
|Uneingeschränkt|Die IP-Schutz Ebene ist uneingeschränkt. Dieser Wert wird von Anwendungen verwendet, die für den gesamten Internet Betrieb entwickelt wurden, einschließlich Anwendungen, die die in Windows integrierten IPv6-NAT-Traversale-Funktionen nutzen (z. b. Teredo). Diese Anwendungen können IPv4-Firewalls umgehen, sodass Anwendungen gegen Internet Angriffe auf den geöffneten Port festgeschrieben werden müssen. Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutz Ebene für einen Socket uneingeschränkt.|  
|Nicht angegeben.|Die IP-Schutz Ebene ist nicht angegeben. Unter Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutz Ebene für einen Socket nicht angegeben.|  
  
 Der Standardwert für das `ipProtectionLevel`-Attribut ist **nicht angegeben**.  
  
 Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `ipProtectionLevel` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie angeben, dass die Abschlussports verwendet werden sollen und dass der Standard <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> uneingeschränkt sein sollte.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
