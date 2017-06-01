---
title: "&lt;socket&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#socket"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<socket>-Element"
  - "socket-Element"
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;socket&gt;-Element (Netzwerkeinstellungen)
Gibt an, ob Socketvorgänge Abschlussanschlüsse verwenden.  
  
## Syntax  
  
```  
  
      <socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel ="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/socket>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`alwaysUseCompletionPortsForAccept`|Gibt an, ob der Socket stets Abschlussanschlüsse für Accept\-Methodenaufrufe verwenden soll.  Der Standardwert ist `false`.|  
|`alwaysUseCompletionPortsForConnect`|Gibt an, ob der Socket stets Abschlussanschlüsse für Connect\-Methodenaufrufe verwenden soll.  Der Standardwert ist `false`.|  
|`ipProtectionLevel`|Gibt den Standardwert für die <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> an, die für ein Socket verwendet werden soll.  Der Standardwert hängt von der Version von Windows ab.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>\-Namespace.|  
  
## Hinweise  
 Die Attribute `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` werden verwendet, um dem Standardverhalten bezüglich der Verwendung von Abschlussanschlüssen anzugeben durch Klassen im <xref:System.Net.Sockets?displayProperty=fullName>.namespace.  Abschlussanschlüsse werden für Hochleistungs\-Serveranwendungen empfohlen.  
  
 Der Standardwert für das `alwaysUseCompletionPortsForAccept`\-Attribut und das `alwaysUseCompletionPortsForConnect`\-Attribut ist **false**.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForAccept`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForConnect`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
 Das `ipProtectionLevel`\-Attribut gibt die Standardeinstellung für <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> an, die für ein Socket verwendet werden soll.  Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>\-Eigenschaft ermöglicht das Konfigurieren einer Einschränkung eines IPv6\-Sockets auf einen angegebenen Bereich, z. B. Adressen mit demselben linklokalen oder standortlokalen Präfix.  Diese Option ermöglicht es Anwendungen, Zugriffsbeschränkungen für IPv6\-Sockets festlegen.  Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen.  Diese Option erweitert oder beschränkt den Bereich eines lauschenden Sockets und ermöglicht so bei Bedarf den uneingeschränkten Zugriff von öffentlichen und privaten Benutzern oder beschränkt den Zugriff nur auf denselben Standort.  
  
 Diese `ipProtectionLevel`\-Attributeinstellung wirkt sich nur auf den ursprünglichen eingehenden Datenverkehr aus:  
  
-   Ein TCP\-Server, der auf eingehende Verbindungen auf einem Socket lauscht.  
  
-   Eine UDP\-Anwendung, die auf einem Socket ein Paket empfängt.  
  
 Diese Konfigurationseinstellung wirkt sich nicht auf bereits hergestellte TCP\-Verbindungen aus \(der Datenverkehr ist in beiden Richtungen uneingeschränkt\), und auch nicht auf eine Anwendung, die UDP\-Pakete sendet.  
  
 Die möglichen Werte für die `ipProtectionLevel`\-Attributeinstellung entsprechen den definierten Schutzebenen, die in der <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>\-Enumeration wie folgt angegeben werden:  
  
|||  
|-|-|  
|**Attributwert**|****Beschreibung****|  
|EdgeRestricted|Die IP\-Schutzebene ist auf den Netzwerk\-Edge beschränkt.  Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind.  Diese Einstellung lässt die NAT\-Überquerung \(Netzwerkadressenübersetzung\) mithilfe der Windows Teredo\-Implementierung nicht zu.  Diese Anwendungen können IPv4\-Firewalls umgehen und müssen daher vor Internetangriffen auf den geöffneten Anschluss geschützt werden.  Unter Windows Server 2003 und Windows XP ist der Standardwert für die IP\-Schutzebene für einen Socket "EdgeRestricted".|  
|Eingeschränkter Zugriff|Die IP\-Schutzebene ist eingeschränkt.  Dieser Wert wird von Intranetanwendungen verwendet, die keine Internetszenarios implementieren.  Diese Anwendungen werden im Allgemeinen nicht getestet oder vor Internetangriffen geschützt.  Diese Einstellung beschränkt den empfangenen Datenverkehr auf linklokalen Datenverkehr.|  
|Uneingeschränkt|Die IP\-Schutzebene ist nicht eingeschränkt.  Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind. Dazu zählen Anwendungen, die in Windows integrierte IPv6\-NAT\-Überquerungsfunktionen nutzen \(z. B. Teredo\).  Diese Anwendungen können IPv4\-Firewalls umgehen und müssen daher vor Internetangriffen auf den geöffneten Anschluss geschützt werden.  Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP\-Schutzebene für einen Socket "Unrestricted".|  
|Nicht angegeben|Die IP\-Schutzebene ist nicht angegeben.  Unter Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP\-Schutzebene für einen Socket "Unspecified".|  
  
 Der Standardwert für das `ipProtectionLevel`\-Attribut ist **Unspecified**.  
  
 Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>\-Eigenschaft kann verwendet werden, um den aktuellen Wert des `ipProtectionLevel`\-Attributs aus anwendbaren Konfigurationsdateien abzurufen.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie Sie angeben können, dass Abschlussanschlüsse verwendet werden sollen und dass die Standardeinstellung für <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> unbeschränkt sein soll.  
  
```  
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
  
## Siehe auch  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Configuration.SocketElement?displayProperty=fullName>   
 <xref:System.Net.Sockets?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)