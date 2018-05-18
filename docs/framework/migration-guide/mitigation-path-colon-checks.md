---
title: 'Entschärfung: Überprüfung von Pfaden auf Doppelpunkte'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a54220a90a5120d13c89232d30ab40140c324097
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-path-colon-checks"></a>Entschärfung: Überprüfung von Pfaden auf Doppelpunkte
Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (im Hinblick auf Länge und Format). Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.  
  
## <a name="impact"></a>Auswirkungen  
 Durch diese Änderungen werden einige URI-Pfade blockiert, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> zuvor unterstützt wurden.  
  
## <a name="mitigation"></a>Minderung  
 Sie können folgendermaßen vorgehen, um das Problem von bisher gültigen Pfaden zu umgehen, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> nicht mehr unterstützt werden:  
  
-   Entfernen Sie manuell das Schema aus einer URL. Entfernen Sie beispielsweise `file://` aus einer URL.  
  
-   Übergeben Sie den URI an einen <xref:System.Uri>-Konstruktor, und rufen Sie den Wert der <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>-Eigenschaft ab.  
  
-   Entscheiden Sie sich gegen die Normalisierung des neuen Pfades, indem Sie den Schalter `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext>auf `true` festlegen.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
