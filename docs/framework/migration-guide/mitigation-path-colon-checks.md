---
title: 'Entschärfung: Überprüfen von Pfaden auf Doppelpunkte'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: e88643fea3bd507289436f41880a2de34117884f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457896"
---
# <a name="mitigation-path-colon-checks"></a>Entschärfung: Überprüfen von Pfaden auf Doppelpunkte
Für Apps, die gezielt .NET Framework 4.6.2 und höhere Versionen verwenden, wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (im Hinblick auf Länge und Format). Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.  
  
## <a name="impact"></a>Auswirkungen  
 Durch diese Änderungen werden einige URI-Pfade blockiert, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> zuvor unterstützt wurden.  
  
## <a name="mitigation"></a>Minderung  
 Sie können folgendermaßen vorgehen, um das Problem von bisher gültigen Pfaden zu umgehen, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> nicht mehr unterstützt werden:  
  
- Entfernen Sie manuell das Schema aus einer URL. Entfernen Sie beispielsweise `file://` aus einer URL.  
  
- Übergeben Sie den URI an einen <xref:System.Uri>-Konstruktor, und rufen Sie den Wert der <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>-Eigenschaft ab.  
  
- Entscheiden Sie sich gegen die Normalisierung des neuen Pfades, indem Sie den Schalter `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext>auf `true` festlegen.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
