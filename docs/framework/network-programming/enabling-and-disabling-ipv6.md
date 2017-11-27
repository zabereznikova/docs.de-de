---
title: Aktivieren und Deaktivieren von IPv6
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 9edb87cf1ee35ac6848a478552cf8d0732177a81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-and-disabling-ipv6"></a>Aktivieren und Deaktivieren von IPv6
Um das IPv6-Protokoll verwenden zu können, stellen Sie sicher, dass eine Betriebssystemversion ausgeführt wird, die IPv6 unterstützt. Stellen Sie zudem sicher, dass das Betriebssystem und die Netzwerkklassen ordnungsgemäß konfiguriert sind.  
  
## <a name="configuration-steps"></a>Konfigurationsschritte  
 In der folgenden Tabelle werden verschiedene Konfigurationen aufgelistet:  
  
|Ist Betriebssystem IPv6-fähig?|Sind Netzwerkklassen IPv6-fähig?|Beschreibung|  
|-------------------------------------|---------------------------------------|-----------------|  
|Nein|Nein|Kann IPv6-Adressen analysieren.|  
|Nein|Ja|Kann IPv6-Adressen analysieren.|  
|Ja|Nein|Kann IPv6-Adressen analysieren und mithilfe von nicht als veraltet markierten Methoden zur Namensauflösung auflösen.|  
|Ja|Ja|Kann IPv6-Adressen analysieren und mithilfe von allen Methoden auflösen, einschließlich der als veraltet markierten Methoden.|  
  
 Bedenken Sie, dass Sie zum Aktivieren der IPv6-Unterstützung für alle Klassen im System.Net-Namespace die Computerkonfigurationsdatei oder die Konfigurationsdatei für die Anwendung ändern müssen. Die Konfigurationsdatei für die Anwendung hat Vorrang vor der Computerkonfigurationsdatei.  
  
 Ein Beispiel zum Ändern der Computerkonfigurationsdatei *machine.config* zur Aktivierung der IPv6-Unterstützung finden Sie unter [How to: Modify the Computer Configuration File to Enable Ipv6 Support (Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung)](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md). Stellen Sie außerdem sicher, dass die IPv6-Unterstützung für das Betriebssystem aktiviert ist.  
  
 .NET Framework verfügt über einen Konfigurationsschalter, der in einer Konfigurationsdatei wie folgt festgelegt ist:  
  
```xml  
<system.net>…  
    <settings>…  
        <ipv6 enabled="true"/>…  
    </settings>…  
</system.net>  
```  
  
 Für .NET Framework Version 1.1 und früher gibt der Wert des Konfigurationsschalters **ipv6 enabled** an, ob Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-Adressen zurückgeben.  
  
 Für .NET Framework Version 2.0 und höher geben Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>-Methode), sofern Windows IPv6 unterstützt, IPv6-Adressen mit einer Einschränkung zurück. Veraltete Member der DNS <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>-Methode) lesen und erkennen den Wert in der Konfigurationsdatei für die IPv6-aktivierte Einstellung.  
  
## <a name="see-also"></a>Siehe auch  
 [Internetprotokoll Version 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [Sockets](../../../docs/framework/network-programming/sockets.md)  
 [Network Settings Schema (Schema für Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [\<IPv6>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
