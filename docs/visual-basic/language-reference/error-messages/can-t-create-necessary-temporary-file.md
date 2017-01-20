---
title: "Can&#39;t create necessary temporary file | Microsoft Docs"
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
  - "vbrID322"
dev_langs: 
  - "VB"
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Can&#39;t create necessary temporary file
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Entweder ist das Laufwerk voll, das das von der TEMP\-Umgebungsvariable angegebene Verzeichnis enthält, oder die TEMP\-Umgebungsvariable gibt ein ungültiges oder schreibgeschütztes Laufwerk oder Verzeichnis an.  
  
### So beheben Sie diesen Fehler  
  
1.  Löschen Sie Dateien auf dem Laufwerk, falls dieses voll ist.  
  
2.  Geben Sie ein anderes Laufwerk in der TEMP\-Umgebungsvariable an.  
  
3.  Geben Sie ein für die TEMP\-Umgebungsvariable gültiges Laufwerk an.  
  
4.  Entfernen Sie die schreibgeschützte Einschränkung vom aktuell angegebenen Laufwerk oder Verzeichnis.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)