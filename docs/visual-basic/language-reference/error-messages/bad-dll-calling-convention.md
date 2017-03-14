---
title: "Bad DLL calling convention | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID49"
dev_langs: 
  - "VB"
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Bad DLL calling convention
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Argumente, die an eine Dynamic Link Library \(DLL\) übergeben werden, müssen mit den Argumenten genau übereinstimmen, die von der Routine erwartet werden.  Aufrufkonventionen enthalten die Nummer, den Typ und die Reihenfolge der Argumente.  Möglicherweise ruft das Programm eine Routine in einer DLL auf, der der falsche Typ oder die falsche Anzahl von Argumenten übergeben wird.  
  
### So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass alle Argumenttypen mit denen, die in der Deklaration der aufgerufenen Routine angegeben sind, übereinstimmen.  
  
2.  Vergewissern Sie sich, dass dieselbe Anzahl an Argumenten übergeben wird, die in der Deklaration der aufgerufenen Routine angegeben sind.  
  
3.  Wenn die DLL\-Routine Argumente nach Wert erwartet, vergewissern Sie sich, dass für diese Argumente `ByVal` in der Deklaration für die Routine angegeben ist.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)