---
title: "Minderung: WPF-Layout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Minderung: WPF-Layout
Das Layout der WPF\-Steuerelemente kann sich leicht ändern.  
  
## Auswirkungen  
 Auswirkungen durch diese Änderung:  
  
-   Die Breite oder Höhe der Elemente vergrößert oder verkleinert sich allenfalls um einen Pixel.  
  
-   Die Platzierung eines Objekts kann sich allenfalls um einen Pixel verschieben.  
  
-   Zentrierte Elemente können sich vertikal oder horizontal um allenfalls ein Pixel von der Mitte verschieben.  
  
 Standardmäßig wird dieses neue Layout nur für Apps aktiviert, die auf .NET Framework 4.6 abzielen.  
  
## Problemumgehung  
 Da durch diese Änderung das Clipping die rechte oder Unterseite von WPF\-Steuerelementen bei hohen DPIs beseitigt wird, können Apps, die auf frühere Versionen von .NET Framework abzielen, aber auf .NET Framework 4.6 ausgeführt werden, dieses neue Verhalten übernehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:  
  
```  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 Apps, die auf .NET Framework 4.6 abzielen, aber WPF\-Steuerelemente zum Rendern mithilfe des vorherigen Layoutalgorithmus verwenden möchten, können dies vornehmen, sofern die folgende Zeile zum Abschnitt `<runtime>` der Datei „app.config“ hinzugefügt wird:  
  
```  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)