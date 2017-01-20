---
title: "Permission denied (Visual Basic) | Microsoft Docs"
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
  - "vbrID70"
dev_langs: 
  - "VB"
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Permission denied (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Es wurde versucht, auf einen schreibgeschützten Datenträger zu schreiben oder auf eine gesperrte Datei zuzugreifen.  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn eine schreibgeschützte Datei geöffnet werden soll, ändern Sie das Schreibschutzattribut der Datei.  
  
2.  Stellen Sie sicher, dass die Datei nicht durch einen anderen Prozess gesperrt wurde, und warten Sie mit dem Öffnen der Datei, bis sie von dem anderen Prozess freigegeben wurde.  
  
3.  Um auf die Registrierung zuzugreifen, prüfen Sie, ob Ihre Benutzerberechtigungen diese Art des Zugriffs auf die Registrierung einschließen.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)