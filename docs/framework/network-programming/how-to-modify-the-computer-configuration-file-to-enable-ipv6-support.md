---
title: "Gewusst wie: &#196;ndern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterst&#252;tzung | Microsoft Docs"
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
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Gewusst wie: &#196;ndern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterst&#252;tzung
Im folgenden Codebeispiel wird gezeigt, wie die Computer\-, *machine.config* ändert, um Unterstützung IPv6 zu aktivieren.  Die Datei *machine.config* wird im Ordner *%Windir%\\Microsoft.NET\\Framework* im Verzeichnis gespeichert, in dem Windows installiert wurde.  Es gibt eine separate Datei *machine.config* in den Ordnern unter *%Windir%\\Microsoft.NET\\Framework* für jede Version von .NET Framework, die auf dem Computer installiert ist \(beispielsweise *C:\\WINDOWS\\Microsoft.NET\\Framework\\v2.0.50727\\machine.config*\).  
  
 Diese Einstellungen können in der Konfigurationsdatei für die Anwendung auch ausgeführt werden, die Vorrang vor der Computerkonfigurationsdatei verfügt.  
  
 Bei .NET Framework Version 1.1 und früher, gibt der Wert des **ipv6 enabled** Konfigurationsschalters ob Member der Adressen der <xref:System.Net.Dns?displayProperty=fullName>\-Klassenrückgabe IPv6 an.  
  
 Bei .NET Framework Version 2.0 und höher, wenn Windows IPv6 unterstützt, dann alle Member der Klasse <xref:System.Net.Dns?displayProperty=fullName> \(beispielsweise, die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName>\-Methode\), gibt Adressen IPv6 mit einer Einschränkung zurück.  Veraltete Member der Klasse <xref:System.Net.Dns?displayProperty=fullName> \(beispielsweise, die <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName>\-Methode\) lesen und erkennen den Wert in der Konfigurationsdatei.  
  
> [!NOTE]
>  Bei .NET Framework Version 2.0 und höher, wird IPv6 standardmäßig aktiviert.  Bei .NET Framework Version 1.1 und früher, wird IPv6 standardmäßig deaktiviert.  
  
## Beispiel  
  
```  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## Siehe auch  
 [IPv6\-Adressierung](../../../docs/framework/network-programming/ipv6-addressing.md)   
 [Netzwerkeinstellungsschema](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)