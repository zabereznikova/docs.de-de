---
title: "Entschärfung: Überprüfung von Pfaden auf Doppelpunkte | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b5e2426fc81c8fd38994a4124cf71af8ec445bfb
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-path-colon-checks"></a>Entschärfung: Überprüfung von Pfaden auf Doppelpunkte
Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (im Hinblick auf Länge und Format). Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.  
  
## <a name="impact"></a>Auswirkungen  
 Durch diese Änderungen werden einige URI-Pfade blockiert, die bisher von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> unterstützt wurden.  
  
## <a name="mitigation"></a>Problemumgehung  
 Sie können folgendermaßen vorgehen, um das Problem von bisher gültigen Pfaden zu umgehen, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> nicht mehr unterstützt werden:  
  
-   Entfernen Sie manuell das Schema aus einer URL. Entfernen Sie beispielsweise `file://` aus einer URL.  
  
-   Übergeben Sie den URI an einen <xref:System.Uri>-Konstruktor, und rufen Sie den Wert der <xref:System.Uri.LocalPath%2A?displayProperty=fullName>-Eigenschaft ab.  
  
-   Entscheiden Sie sich gegen die Normalisierung des neuen Pfades, indem Sie den Schalter `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> auf `true` festlegen.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

