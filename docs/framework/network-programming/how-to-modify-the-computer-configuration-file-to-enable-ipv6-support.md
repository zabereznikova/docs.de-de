---
title: 'Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung'
description: Hier erfahren Sie, wie Sie die Computerkonfigurationsdatei „machine.config“ ändern, um die IPv6-Unterstützung im .NET Framework zu ermöglichen.
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
ms.openlocfilehash: eb7b3665c0dbcf0edefa8c48a9e69297d7259067
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502521"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a>Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung
Das folgende Codebeispiel zeigt, wie Sie die Computerkonfigurationsdatei *machine.config* ändern, um die IPv6-Unterstützung zu aktivieren. Die Datei *machine.config* ist im Ordner *%Windir%\Microsoft.NET\Framework* in dem Verzeichnis gespeichert, in dem Windows installiert wurde. Es gibt für jede Version von .NET Framework, die auf dem Computer installiert ist, eine eigene Datei *machine.config* in den Unterordnern von *%Windir%\Microsoft.NET\Framework* (z.B. *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).  
  
 Diese Einstellungen können auch in der Konfigurationsdatei für die Anwendung vorgenommen werden. Die Anwendungskonfigurationsdatei hat Vorrang vor der Computerkonfigurationsdatei.  
  
 Für .NET Framework Version 1.1 und früher gibt der Wert des Konfigurationsschalters **ipv6 enabled** an, ob Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-Adressen zurückgeben.  
  
 Für .NET Framework Version 2.0 und höher geben alle Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>-Methode), sofern Windows IPv6 unterstützt, IPv6-Adressen mit einer Einschränkung zurück. Veraltete Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>-Methode) lesen und erkennen den Wert in der Konfigurationsdatei.  
  
> [!NOTE]
> Für .NET Framework Version 2.0 und höher ist IPv6 standardmäßig aktiviert. Für .NET Framework Version 1.1 und früher ist IPv6 standardmäßig deaktiviert.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>
    ……………  
    </settings>  
    ………………  
</system.net>  
```  
  
## <a name="see-also"></a>Siehe auch

- [IPv6-Adressierung](ipv6-addressing.md)
- [Network Settings Schema (Schema für Netzwerkeinstellungen)](../configure-apps/file-schema/network/index.md)
- [\<ipv6>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
