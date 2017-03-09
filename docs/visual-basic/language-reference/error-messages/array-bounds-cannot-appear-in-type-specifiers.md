---
title: "Array bounds cannot appear in type specifiers | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30638"
  - "bc30638"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30638"
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Array bounds cannot appear in type specifiers
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Arraygrößen können nicht als Teil eines Datentypspezifizierers deklariert werden.  
  
 **Fehler\-ID:** BC30638  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie die Größe des Arrays unmittelbar hinter dem Variablennamen anstatt hinter dem Typ an, wie im folgenden Beispiel dargestellt.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel dargestellt.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)