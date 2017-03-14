---
title: "Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30941"
  - "vbc30941"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30941"
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Structure &#39;&lt;structurename&gt;&#39; must contain at least one instance member variable or at least one instance event declaration not marked &#39;Custom&#39;
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Strukturdefinition schließt keine nicht freigegebenen Variablen oder nicht freigegebenen nicht benutzerdefinierten Ereignisse ein.  
  
 Jede Struktur muss entweder eine Variable oder ein Ereignis enthalten, das auf jede spezifische Instanz \(nicht freigegeben\) statt auf alle Instanzen gemeinsam \([Shared](../../../visual-basic/language-reference/modifiers/shared.md)\) angewendet wird.  Nicht freigegebene Konstanten, Eigenschaften und Prozeduren genügen dieser Anforderung nicht.  Gibt es darüber hinaus keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis, kann es sich bei diesem Ereignis nicht um ein `Custom`\-Ereignis handeln.  
  
 **Fehler\-ID:** BC30941  
  
### So beheben Sie diesen Fehler  
  
-   Definieren Sie mindestens eine Variable oder ein Ereignis, die bzw. das nicht `Shared` ist.  Wenn Sie nur ein Ereignis definieren, muss es nicht benutzerdefiniert sowie nicht freigegeben sein.  
  
## Siehe auch  
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [How to: Declare a Structure](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)