---
title: 'Entschärfung: WPF-Layout'
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: 7a074698fd203d0c5f9b799bfee8a6a9cb40800e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457782"
---
# <a name="mitigation-wpf-layout"></a>Entschärfung: WPF-Layout
Das Layout der WPF-Steuerelemente kann sich leicht ändern.  
  
## <a name="impact"></a>Auswirkungen  
 Auswirkungen durch diese Änderung:  
  
- Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.  
  
- Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.  
  
- Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.  
  
 Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.  
  
## <a name="mitigation"></a>Minderung  
 Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Apps, die auf .NET Framework 4.6 abzielen, aber WPF-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a>Siehe auch

- [Anwendungskompatibilität](application-compatibility.md)
