---
title: "Clipboard format is not valid | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID460"
dev_langs: 
  - "VB"
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Clipboard format is not valid
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das angegebene Format der Zwischenablage ist nicht mit der ausgeführten Methode kompatibel.  Dieser Fehler kann folgende Ursachen haben:  
  
-   Verwenden der `GetText`\-Methode oder der `SetText`\-Methode der Zwischenablage mit einem anderen Zwischenablageformat als `vbCFText` oder `vbCFLink`.  
  
-   Verwenden der `GetData`\-Methode oder der `SetData`\-Methode der Zwischenablage mit einem anderen Zwischenablageformat als `vbCFBitmap`, `vbCFDIB` oder `vbCFMetafile`.  
  
-   Verwenden der `GetData`\-Methode oder der `SetData`\-Methode von `DataObject` mit einem Zwischenablageformat im Bereich, der von Microsoft Windows für registrierte Formate \(&HC000\-&HFFFF\) reserviert ist, obwohl dieses Zwischenablagenformat nicht für Microsoft Windows registriert wurde.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das ungültige Format, und geben Sie ein gültiges Format an.  
  
## Siehe auch  
 [Zwischenablage: Hinzufügen anderer Formate](../Topic/Clipboard:%20Adding%20Other%20Formats.md)