---
title: '&lt;Socket&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: "21"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: fefb8e119d428d86501e1c8cdd5eec5ef0809cbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsocketgt-element-network-settings"></a>&lt;Socket&gt; -Element (Netzwerkeinstellungen)
Gibt an, ob es sich bei Socketvorgänge Abschlussports verwenden.  
  
 \<configuration>  
\<System.NET >  
\<Einstellungen >  
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
|`alwaysUseCompletionPortsForAccept`|Gibt an, ob der Socket immer Abschlussports für Accept-Methodenaufrufe verwenden soll. Der Standardwert ist `false`.|  
|`alwaysUseCompletionPortsForConnect`|Gibt an, ob der Socket immer Abschlussports für Connect-Methodenaufrufe verwenden soll. Der Standardwert ist `false`.|  
|`ipProtectionLevel`|Gibt die standardmäßige <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für ein Socket verwendet. Der Standardwert hängt von der Version von Windows ab.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|---------------------|  
|[Einstellungen](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.|  
  
## <a name="remarks"></a>Hinweise  
 Die `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` Attribute werden an das standardmäßige Verhalten bezüglich der Verwendung von Abschlussports verwendet, durch die Klassen in der <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace. Für hohe Leistung serveranwendungen werden Abschlussports empfohlen.  
  
 Der Standardwert für die `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` Attribute **"false"**.  
  
 Die <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> können verwendet werden, um den aktuellen Wert der Abrufen der `alwaysUseCompletionPortsForAccept` Attribut aus anwendbaren Konfigurationsdateien. Die <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> können verwendet werden, um den aktuellen Wert der Abrufen der `alwaysUseCompletionPortsForConnect` Attribut aus anwendbaren Konfigurationsdateien.  
  
 Die `ipProtectionLevel` Attribut gibt die standardmäßige <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für ein Socket verwendet. Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft ermöglicht die Konfiguration einer Einschränkung eines IPv6-Sockets auf einen angegebenen Bereich, z. B. Adressen mit demselben linklokalen oder standortlokalen Präfix. Diese Option ermöglicht Anwendungen zugriffseinschränkungen für IPv6-Sockets zu platzieren. Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen. Diese Option erweitert oder beschränkt den Bereich eines empfangsbereiten Sockets und ermöglicht den uneingeschränkten Zugriff von öffentlichen und privaten Benutzern oder beschränkt den Zugriff nur auf denselben Standort.  
  
 Dies `ipProtectionLevel` attributeinstellung betrifft nur die ersten eingehenden Datenverkehr:  
  
-   Ein TCP-Server für eingehende Verbindungen für ein Socket überwacht.  
  
-   Ein UDP-Anwendung empfangen eines Pakets auf einem Socket.  
  
 Diese Einstellung wirkt sich nicht auf bereits eingerichtete TCP-Verbindungen (Datenverkehr ist nicht eingeschränkt in beide Richtungen) und wirkt sich nicht auf eine Anwendung, die UDP-Pakete zu senden.  
  
 Die möglichen Werte für die `ipProtectionLevel` attributeinstellung entsprechen, mit der definierten Schutzebenen angegeben, der <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> Enumeration wie folgt:  
  
|**Attributwert**|**Beschreibung**|  
|-|-|  
|EdgeRestricted|Die IP-Schutzebene ist Edge beschränkt. Dieser Wert würde von Anwendungen, die für den Betrieb über das Internet verwendet werden. Diese Einstellung lässt keine (Network Address Translation, NAT)-Durchlauf mit der Windows-Teredo-Implementierung. IPv4-Firewalls, diese Anwendungen möglicherweise umgangen werden, damit Anwendungen gegen Angriffe aus dem Internet auf den geöffneten Port weitergeleitet festgeschrieben werden müssen. Unter Windows Server 2003 und Windows XP ist der Standardwert für die IP-Schutzebene für ein Socket Edge beschränkt.|  
|Eingeschränkter Zugriff|Die IP-Schutzebene ist eingeschränkt. Dieser Wert wird von Intranetanwendungen verwendet werden, die keine Internetszenarien implementieren. Diese Anwendungen sind im Allgemeinen nicht getestet oder gegen Internet-ähnliche Angriffe möglichst reduziert. Diese Einstellung wird den empfangenen Datenverkehr verbindungslokale nur eingeschränkt.|  
|Uneingeschränkt|Die IP-Schutzebene ist nicht eingeschränkt. Dieser Wert von Anwendungen, die für den Betrieb über das Internet, einschließlich Anwendungen profitieren von integrierten Funktionen für IPv6-NAT-Durchlauf verwendet werden würde in Windows (z. B. Teredo). IPv4-Firewalls, diese Anwendungen möglicherweise umgangen werden, damit Anwendungen gegen Angriffe aus dem Internet auf den geöffneten Port weitergeleitet festgeschrieben werden müssen. Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutzebene für ein Socket nicht eingeschränkt.|  
|Nicht angegeben.|Die IP-Schutzebene ist nicht angegeben. Unter Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutzebene für ein Socket nicht angegeben.|  
  
 Der Standardwert für die `ipProtectionLevel` -Attribut ist **Unspecified**.  
  
 Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft kann verwendet werden, den aktuellen Wert der abzurufenden der `ipProtectionLevel` Attribut aus anwendbaren Konfigurationsdateien.  
  
## <a name="configuration-files"></a>Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie angegeben, dass Abschlussports verwendet werden soll und dass der Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> nicht eingeschränkt werden soll.  
  
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
