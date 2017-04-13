---
title: "Minderung: Rendern von WPF-Fenstern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Minderung: Rendern von WPF-Fenstern
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], das auf Windows 8 und höher ausgeführt wird, wird das gesamte Fenster ohne Clipping gerendert, wenn es in einem Szenario mit mehreren Monitoren außerhalb einer einzelnen Anzeige liegt.  
  
## Auswirkungen  
 Im Allgemeinen handelt es sich beim Rendering eines Fensters über mehrere Monitore hinweg ohne Clipping um ein erwartetes Verhalten.  Unter Windows 7 und früher ist jedoch ein Clipping der WPF\-Fenster zu beobachten, wenn sie über eine einzelne Anzeige hinausgehen, da sich das Rendern einer Teilmenge des Fensters für einen zweiten Monitor erheblich auf die Leistung auswirkt.  
  
 Die Auswirkung des Renderings von WPF\-Fenstern über Monitore unter Windows 8 hinweg, lässt sich nicht genau quantifizieren, da es von einer Vielzahl von Faktoren abhängt.  In einigen Fällen führt dies möglicherweise weiterhin zu einer unerwünschten Auswirkung hinsichtlich der Leistung, insbesondere für Benutzer, die grafikintensive Anwendungen ausführen und über Fenster verfügen, die sich über mehrere Monitore hinweg erstrecken.  In anderen Fällen möchten Sie möglicherweise einfach ein einheitliches Verhalten über .NET Framework\-Versionen hinweg sicherstellen.  
  
## Problemumgehung  
 Sie können diese Änderung deaktivieren und das vorherige Verhalten des Clippings eines WPF\-Fensters wiederherstellen, wenn es über eine einzelne Anzeige hinausgeht.  Hierfür gibt es zwei Möglichkeiten:  
  
-   Durch das Hinzufügen des `<EnableMultiMonitorDisplayClipping>`\-Elements zum Abschnitt `<appSettings>` Ihrer Anwendungskonfigurationsdatei können Sie dieses Verhalten in Apps auf Windows 8 oder höher deaktivieren oder aktivieren.  Beispielsweise deaktiviert der folgende Konfigurationsabschnitt das Rendering ohne Clipping:  
  
    ```  
  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
  
    ```  
  
     Die `<EnableMultiMonitorDisplayClipping>`\-Konfigurationseinstellung kann einen der zwei Werte aufweisen:  
  
    -   `true`, um das Clipping bei Fenstern zu aktivieren, um Grenzen beim Rendering zu überwachen.  
  
    -   `false`, um das Clipping bei Fenstern zu deaktivieren, um Grenzen beim Rendering zu überwachen.  
  
-   Durch das Festlegen der <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A>\-Eigenschaft auf `true` beim Starten der App.  
  
## Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)