---
title: "Number of indices exceeds the number of dimensions of the indexed array | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30106"
  - "vbc30106"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30106"
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Number of indices exceeds the number of dimensions of the indexed array
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Die Anzahl der Indizes, die für den Zugriff auf ein Arrayelement verwendet wird, muss mit dem Rang des Arrays genau übereinstimmen, d. h. mit der Anzahl der dafür deklarierten Dimensionen.  
  
 **Fehler\-ID:** BC30106  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie Indizes aus dem Arrayverweis, bis die gesamte Anzahl an Indizes mit dem Rang des Arrays übereinstimmt.  Beispiele:  
  
    ```  
    [Visual Basic]  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)