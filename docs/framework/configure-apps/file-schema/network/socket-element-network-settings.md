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
ms.openlocfilehash: b8df32745007b2a145d35b8cfcc4cbd2bd17eb33
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201732"
---
# <a name="socket-element-network-settings"></a>\<socket>-Element (Netzwerkeinstellungen)

Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

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
|`alwaysUseCompletionPortsForAccept`|Gibt an, ob der Socket immer Beendigungs Anschlüsse für Accept-Methodenaufrufe verwenden soll. Standardwert: `false`.|  
|`alwaysUseCompletionPortsForConnect`|Gibt an, ob der Socket immer Beendigungs Anschlüsse für Verbindungsmethoden Aufrufe verwenden soll. Standardwert: `false`.|  
|`ipProtectionLevel`|Gibt den Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> an, der für einen Socket verwendet werden soll. Der Standardwert hängt von der Windows-Version ab.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Bemerkungen  

 Das `alwaysUseCompletionPortsForAccept` -Attribut und das- `alwaysUseCompletionPortsForConnect` Attribut werden verwendet, um das Standardverhalten in Bezug auf die Verwendung von Abschlussports durch die Klassen im <xref:System.Net.Sockets?displayProperty=nameWithType> .-Namespace anzugeben. Abschlussports werden für hochleistungsfähige Server Anwendungen empfohlen.  
  
 Der Standardwert für das `alwaysUseCompletionPortsForAccept` -Attribut und das- `alwaysUseCompletionPortsForConnect` Attribut ist **false**.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>Kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForAccept` Attributs aus anwendbaren Konfigurationsdateien zu erhalten. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>Kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForConnect` Attributs aus anwendbaren Konfigurationsdateien zu erhalten.  
  
 Das- `ipProtectionLevel` Attribut gibt den <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für einen Socket zu verwendenden Standardwert an. Die- <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft ermöglicht die Konfiguration einer Einschränkung für einen IPv6-Socket zu einem angegebenen Bereich, z. b. Adressen mit demselben Link lokalen oder Standort lokalen Präfix. Mit dieser Option können Anwendungen Zugriffs Einschränkungen für IPv6-Sockets platzieren. Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen. Mit dieser Option wird der Bereich eines Abhör Sockets erweitert oder eingeschränkt, bei Bedarf der uneingeschränkte Zugriff von öffentlichen und privaten Benutzern ermöglicht oder der Zugriff auf dieselbe Website eingeschränkt.  
  
 Diese `ipProtectionLevel` Attribut Einstellung betrifft nur den ersten eingehenden Datenverkehr:  
  
- Ein TCP-Server, der eingehende Verbindungen für einen Socket überwacht.  
  
- Eine UDP-Anwendung, die ein Paket für einen Socket empfängt.  
  
 Diese Konfigurationseinstellung wirkt sich nicht auf bereits festgelegte TCP-Verbindungen aus (Datenverkehr ist in beiden Richtungen uneingeschränkt) und wirkt sich nicht auf eine Anwendung aus, die UDP-Pakete sendet.  
  
 Die möglichen Werte für die- `ipProtectionLevel` Attribut Einstellung entsprechen den definierten, in der-Enumeration angegebenen Schutz Ebenen <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> wie folgt:  
  
|**Attributwert**|**Beschreibung**|  
|-|-|  
|Edgerestrihiert|Die IP-Schutzebene ist auf den Netzwerk-Edge beschränkt. Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind. Diese Einstellung lässt die NAT-Überquerung (Netzwerkadressenübersetzung) mithilfe der Windows Teredo-Implementierung nicht zu. Diese Anwendungen können IPv4-Firewalls umgehen und müssen daher vor Internetangriffen auf den geöffneten Anschluss geschützt werden. Unter Windows Server 2003 und Windows XP ist der Standardwert für die IP-Schutzebene für einen Socket "EdgeRestricted".|  
|Eingeschränkt|Die IP-Schutzebene ist eingeschränkt. Dieser Wert wird von Intranetanwendungen verwendet, die keine Internetszenarios implementieren. Diese Anwendungen werden im Allgemeinen nicht getestet oder vor Internetangriffen geschützt. Diese Einstellung beschränkt den empfangenen Datenverkehr auf linklokalen Datenverkehr.|  
|Nicht eingeschränkt|Die IP-Schutzebene ist nicht eingeschränkt. Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind. Dazu zählen Anwendungen, die in Windows integrierte IPv6-NAT-Überquerungsfunktionen nutzen (z. B. Teredo). Diese Anwendungen können IPv4-Firewalls umgehen und müssen daher vor Internetangriffen auf den geöffneten Anschluss geschützt werden. Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutzebene für einen Socket "Unrestricted".|  
|Nicht angegeben.|Die IP-Schutzebene ist nicht angegeben. Unter Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutzebene für einen Socket "Unspecified".|  
  
 Der Standardwert für das- `ipProtectionLevel` Attribut ist **nicht angegeben**.  
  
 Die- <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert des `ipProtectionLevel` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  

 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Abschlussports verwendet werden sollen und der Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> uneingeschränkt sein sollte.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](index.md)
