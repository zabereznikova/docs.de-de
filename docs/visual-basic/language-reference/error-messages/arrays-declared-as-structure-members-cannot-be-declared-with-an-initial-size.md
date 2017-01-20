---
title: "Arrays declared as structure members cannot be declared with an initial size | Microsoft Docs"
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
  - "vbc31043"
  - "bc31043"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31043"
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Arrays declared as structure members cannot be declared with an initial size
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Array in einer Struktur wird mit einer vorgegebenen Größe deklariert.  Sie können nicht jedes beliebige Strukturelement initialisieren, die Deklaration einer Arraygröße ist jedoch eine Form von Initialisierung.  
  
 **Fehler\-ID:** BC31043  
  
### So beheben Sie diesen Fehler  
  
1.  Definieren Sie das Array in der Struktur als dynamisch \(keine vorgegebene Größe\).  
  
2.  Wenn ein Array bestimmter Größe benötigt wird, kann die Größe des dynamischen Arrays während der Codeausführung mit einer [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) verändert werden.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [How to: Declare a Structure](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)