---
title: '&lt;Socket&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 0e36b7c72631406293e76b185c9836ed9ffec328
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044878"
---
# <a name="ltsocketgt-element-network-settings"></a>&lt;Socket&gt; -Element (Netzwerkeinstellungen)
Gibt an, ob es sich bei Socketvorgänge Abschlussports verwenden.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<Socket >  
  
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
|`alwaysUseCompletionPortsForAccept`|Gibt an, ob der Socket immer Komplettierungsports für Accept-Methodenaufrufe verwenden soll. Der Standardwert ist `false`.|  
|`alwaysUseCompletionPortsForConnect`|Gibt an, ob der Socket immer Komplettierungsports für Connect Methodenaufrufe verwenden soll. Der Standardwert ist `false`.|  
|`ipProtectionLevel`|Gibt die Standardvordergrundfarbe für <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für einen Socket verwenden. Der Standardwert hängt von der Version von Windows.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Die `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` Attribute werden an das Standardverhalten in Bezug auf die Verwendung von Abschlussanschlüsse verwendet, von den Klassen in der <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace. Abschlussports werden für Anwendungen mit hoher Leistungsfähigkeit Server empfohlen.  
  
 Der Standardwert für die `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` Attribute **"false"**.  
  
 Die <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> können verwendet werden, um den aktuellen Wert der erste der `alwaysUseCompletionPortsForAccept` Attribut aus anwendbaren Konfigurationsdateien. Die <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> können verwendet werden, um den aktuellen Wert der erste der `alwaysUseCompletionPortsForConnect` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Die `ipProtectionLevel` Attribut gibt die Standardvordergrundfarbe für <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für einen Socket verwenden. Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> -Eigenschaft ermöglicht das Konfigurieren einer Einschränkung eines IPv6-Sockets auf einen angegebenen Bereich, z. B. Adressen mit demselben linklokalen oder standortlokalen Präfix. Diese Option ermöglicht es Anwendungen zugriffseinschränkungen für IPv6-Sockets zu platzieren. Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen. Diese Option erweitert oder beschränkt den Bereich eines empfangsbereiten Sockets, ermöglicht uneingeschränkten Zugriff von öffentlichen und privaten Benutzern bei Bedarf oder Einschränken des Zugriffs nur auf die denselben Standort erforderlich.  
  
 Dies `ipProtectionLevel` attributeinstellung wirkt sich auf nur die ersten eingehenden Datenverkehr:  
  
-   Ein TCP-Server lauscht für eingehende Verbindungen für einen Socket.  
  
-   Eine UDP-Anwendung empfangen eines Pakets auf einem Socket.  
  
 Diese Einstellung wirkt sich nicht auf bereits eingerichtete TCP-Verbindungen (Datenverkehr ist in beide Richtungen unrestricted) und wirkt sich nicht auf eine Anwendung, die UDP-Pakete zu senden.  
  
 Die möglichen Werte für die `ipProtectionLevel` Einstellung des Attributs entsprechen den Werten der definierten Schutzebenen angegeben, der <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> Enumeration wie folgt:  
  
|**Attributwert**|**Beschreibung**|  
|-|-|  
|EdgeRestricted|Die IP-Schutzebene ist Edge beschränkt. Dieser Wert wird von Anwendungen entwickelt, um den Betrieb über das Internet verwendet werden. Diese Einstellung lässt keine (Network Address Translation, NAT) durchlaufen, die unter Verwendung der Windows Teredo-Implementierung. Diese Anwendungen können IPv4-Firewalls umgehen, damit Anwendungen vor auf den geöffneten Anschluss geleitet Internetangriffen geschützt werden müssen. Unter Windows Server 2003 und Windows XP ist der Standardwert für die IP-Schutzebene für einen Socket-Edge beschränkt.|  
|Eingeschränkter Zugriff|Die IP-Schutzebene ist eingeschränkt. Dieser Wert wird von Intranetanwendungen verwendet werden, die keine Internetszenarios implementieren. Diese Anwendungen sind im Allgemeinen nicht getestet oder Angriffe Internetformat festgeschrieben. Diese Einstellung wird den empfangenen Datenverkehr auf linklokalen beschränkt.|  
|Uneingeschränkt|Die IP-Schutzebene ist nicht eingeschränkt. Dieser Wert wird von Anwendungen entwickelt, um den Betrieb über das Internet, einschließlich Anwendungen profitieren von IPv6-NAT-Traversal-Funktionen integriert in Windows (z. B. Teredo). Diese Anwendungen können IPv4-Firewalls umgehen, damit Anwendungen vor auf den geöffneten Anschluss geleitet Internetangriffen geschützt werden müssen. Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutzebene für einen Socket nicht eingeschränkt.|  
|Nicht angegeben.|Die IP-Schutzebene ist nicht angegeben. Auf Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutzebene für einen Socket nicht angegeben.|  
  
 Der Standardwert für die `ipProtectionLevel` Attribut **Unspecified**.  
  
 Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `ipProtectionLevel` Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie angeben, dass Abschlussanschlüsse verwendet werden soll und dass der Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> sollte nicht eingeschränkt werden.  
  
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
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
