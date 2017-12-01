---
title: "Optimierung für freigegebenes Webhosting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a>Optimierung für freigegebenes Webhosting
Wenn Sie eine Server-Administrator, die sind durch das Hosten von mehreren kleinen Websites gemeinsam verwendet wird, können Sie Optimieren der Leistung und Websitekapazität erhöhen, indem Sie den folgenden Code `gcTrimCommitOnLowMemory` zum Festlegen der `runtime` Knoten in der Aspnet.config-Datei in .NET Verzeichnis:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Diese Einstellung ist nur für freigegebene Web empfohlen Hostingszenarien.  
  
 Da der Garbage Collector den Speicher für zukünftige belegungen bereit beibehält, kann seine belegter Speicher mehr als unbedingt erforderlich ist. Sie können diesen Speicher angepasst Zeiten reduzieren bei hoher Auslastung auf dem Systemspeicher. Reduzierung des belegten Speichers verbessert die Leistung und erweitert die Kapazität für mehrere Websites hosten.  
  
 Wenn die `gcTrimCommitOnLowMemory` aktiviert ist, wird der Garbage Collector wertet die Arbeitsspeicher-Systemlast und einen Modus eingibt, wenn die Last über 90 % erreicht. Dabei wird der Modus beibehalten, bis wieder die Last unter 85 % liegt.  
  
 Wenn Umstände es erlauben, kann der Garbage Collector entscheiden, die die `gcTrimCommitOnLowMemory` Einstellung nicht die aktuelle Anwendung helfen und ignorieren Sie ihn.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML-Fragment zeigt, wie zum Aktivieren der `gcTrimCommitOnLowMemory` Einstellung. Ellipsen kennzeichnen andere Einstellungen, die bei der `runtime` Knoten.  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
