---
title: "This array is fixed or temporarily locked (Visual Basic) | Microsoft Docs"
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
  - "vbrID10"
dev_langs: 
  - "VB"
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# This array is fixed or temporarily locked (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Verwendung von `ReDim` zur Änderung der Anzahl von Elementen eines Arrays mit fester Größe.  
  
-   Neudimensionierung eines dynamischen Arrays auf Modulebene, in dem ein Element als Argument an eine Prozedur übergeben wird.  Wenn ein Element übergeben wird, wird das Array gesperrt, um zu vermeiden, dass Speicher für den Verweisparameter innerhalb der Prozedur freigegeben wird.  
  
-   Sie haben versucht, einer `Variant`\-Variablen mit einem Array einen Wert zuzuweisen, `Variant` ist jedoch zurzeit gesperrt.  
  
### So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie das Originalarray innerhalb einer Prozedur mit `ReDim` als dynamisch und nicht als unveränderlich, oder deklarieren Sie es auf Modulebene, ohne die Anzahl der Elemente anzugeben.  
  
2.  Stellen Sie fest, ob Sie dieses Element wirklich übergeben müssen, da es in allen Prozeduren im Modul sichtbar ist.  
  
3.  Finden Sie heraus, wodurch `Variant` gesperrt wird, und beheben Sie das Problem.  
  
## Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)