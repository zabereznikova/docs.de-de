---
title: "File already open | Microsoft Docs"
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
  - "vbrID55"
dev_langs: 
  - "VB"
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# File already open
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Manchmal muss eine Datei geschlossen werden, bevor eine andere `FileOpen`\-Aktion oder eine andere Operation ausgeführt werden kann.  Dieser Fehler kann folgende Ursachen haben:  
  
-   Eine sequenzielle `FileOpen`\-Ausgabemodusoperation wurde für eine Datei ausgeführt, die bereits geöffnet ist.  
  
-   Eine Anweisung verweist auf eine geöffnete Datei.  
  
### So beheben Sie diesen Fehler  
  
1.  Schließen Sie die Datei, bevor Sie die Anweisung ausführen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>