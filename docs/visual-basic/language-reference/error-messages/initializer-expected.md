---
title: "Initializer expected | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30996"
  - "bc30996"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30996"
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Initializer expected
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie haben versucht, eine Instanz einer Klasse mithilfe eines Objektinitialisierers zu deklarieren, dessen Initialisierungsliste leer ist. Dies wird in folgendem Beispiel dargestellt.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 In der Initialisierungsliste muss, wie im folgenden Beispiel gezeigt, mindestens ein Feld oder eine Eigenschaft initialisiert sein.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Fehler\-ID:** BC30996  
  
### So beheben Sie diesen Fehler  
  
1.  Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer, oder verwenden Sie keinen Objektinitialisierer.  
  
## Siehe auch  
 [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)