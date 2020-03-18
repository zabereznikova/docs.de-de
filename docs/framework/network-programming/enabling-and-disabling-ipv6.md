---
title: Aktivieren und Deaktivieren von IPv6
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 66c802dd5feb865faf7469cb7da04fbffcb4a2d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048565"
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
  
 Ein Beispiel zum Ändern der Computerkonfigurationsdatei *machine.config* zur Aktivierung der IPv6-Unterstützung finden Sie unter [How to: Modify the Computer Configuration File to Enable Ipv6 Support (Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung)](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md). Stellen Sie außerdem sicher, dass die IPv6-Unterstützung für das Betriebssystem aktiviert ist.  
  
 .NET Framework verfügt über einen Konfigurationsschalter, der in einer Konfigurationsdatei wie folgt festgelegt ist:  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 Für .NET Framework Version 1.1 und früher gibt der Wert des Konfigurationsschalters **ipv6 enabled** an, ob Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-Adressen zurückgeben.  
  
 Für .NET Framework Version 2.0 und höher geben Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>-Methode), sofern Windows IPv6 unterstützt, IPv6-Adressen mit einer Einschränkung zurück. Veraltete Member der DNS <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>-Methode) lesen und erkennen den Wert in der Konfigurationsdatei für die IPv6-aktivierte Einstellung.  
  
## <a name="see-also"></a>Weitere Informationen

- [Internetprotokoll Version 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../configure-apps/file-schema/network/index.md)
- [\<IPv6>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
