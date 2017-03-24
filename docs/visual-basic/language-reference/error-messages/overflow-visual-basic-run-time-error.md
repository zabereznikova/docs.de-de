---
title: "Overflow (Visual Basic Run-Time Error) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrERRID_Overflow"
dev_langs: 
  - "VB"
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Overflow (Visual Basic Run-Time Error)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Überlauf tritt auf, wenn Sie etwas zuzuweisen versuchen, das die zulässige Größe überschreitet.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Ergebnisse von Zuweisungen, Berechnungen und Datentypkonvertierungen nicht zu lang sind, um im zulässigen Variablenbereich für diesen Werttyp dargestellt zu werden. Weisen Sie den Wert ggf. einem Variablentyp zu, der einen größeren Wertebereich aufnehmen kann.  
  
2.  Vergewissern Sie sich, dass Eigenschaftenzuweisungen für den Eigenschaftenbereich geeignet sind, dem sie zugewiesen werden.  
  
3.  Stellen Sie sicher, dass in Berechnungen verwendete Zahlen, deren Konvertierung in ganze Zahlen erzwungen wird, keine größeren Ergebnisse als ganze Zahlen haben.  
  
## Siehe auch  
 <xref:System.Int32.MaxValue?displayProperty=fullName>   
 <xref:System.Double.MaxValue?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)