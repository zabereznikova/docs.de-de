---
title: "Aktivieren und Deaktivieren von IPv6 | Microsoft Docs"
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
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Aktivieren und Deaktivieren von IPv6
Um das Protokoll IPv6 zu verwenden Sie sicherstellen, dass Sie eine Version des Betriebssystems ausführen das IPv6 unterstützt und sicherzustellen dass das Betriebssystem und die Netzwerkfunktionsklassen ordnungsgemäß konfiguriert werden.  
  
## Konfigurationsschritte  
 In der folgenden Tabelle werden verschiedene Konfigurationen auf  
  
|Betriebssystem IPv6\-enabled?|Netzwerkfunktionen Klasse IPv6\-enabled?|Description|  
|-----------------------------------|----------------------------------------------|-----------------|  
|Nein|Nein|Kann Adressen IPv6 analysieren.|  
|Nein|Ja|Kann Adressen IPv6 analysieren.|  
|Ja|Nein|Kann Adressen IPv6 analysieren und Adressen IPv6 mit markierten veralteten der Namensauflösungsmethoden nicht auflösen.|  
|Ja|Ja|Adressen IPv6 mithilfe aller Methoden einschließlich der analysieren und beheben kann als veraltet gekennzeichnet.|  
  
 Beachten Sie, dass, um die Unterstützung IPv6 für alle Klassen im System.Net\-Namespace zu aktivieren, Sie die Computerkonfigurationsdatei oder die Konfigurationsdatei der Anwendung ändern müssen.  Die Konfigurationsdatei einer Anwendung hat Vorrang vor der Computerkonfigurationsdatei.  
  
 Ein Beispiel, wie die Computer\-, *machine.config* ändert, um Unterstützung zu aktivieren Ipv6 finden, [Gewusst wie: Ändern Sie die Computerkonfigurations\-Datei, um Unterstützung zu aktivieren Ipv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  Stellen Sie außerdem sicher, dass die Unterstützung IPv6 für das Betriebssystem aktiviert ist.  
  
 . .NET Framework verfügt über einen Konfigurationsschalter, der wie folgt in einer Konfigurationsdatei festgelegt wird  
  
```  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 Bei .NET Framework Version 1.1 und früher, gibt der Wert des **ipv6 enabled** Konfigurationsschalters ob Member der Adressen der <xref:System.Net.Dns?displayProperty=fullName>\-Klassenrückgabe IPv6 an.  
  
 Bei .NET Framework Version 2.0 und höher, wenn Windows IPv6 unterstützt, dann Member der Klasse, <xref:System.Net.Dns?displayProperty=fullName> \(beispielsweise, die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=fullName>\-Methode\), gibt Adressen IPv6 mit einer Einschränkung zurück.  Veraltete Member des DNS <xref:System.Net.Dns?displayProperty=fullName> \(beispielsweise, die <xref:System.Net.Dns.Resolve%2A?displayProperty=fullName>\-Methode\) lesen und erkennen den Wert in der Konfigurationsdatei für die ipv6 aktivierten Einstellung.  
  
## Siehe auch  
 [Internetprotokoll Version 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)   
 [Netzwerkeinstellungsschema](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<ipv6\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)