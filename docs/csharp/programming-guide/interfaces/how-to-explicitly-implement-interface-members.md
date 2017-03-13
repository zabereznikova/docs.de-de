---
title: "Gewusst wie: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Schnittstellen [C#], Explizit implementieren"
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Gewusst wie: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)
In diesem Beispiel werden die [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) `IDimensions` und die Klasse `Box` deklariert, womit die Schnittstellenmember `getLength` und `getWidth` explizit implementiert werden.  Auf die Member wird über die `dimensions`\-Schnittstelleninstanz zugegriffen.  
  
## Beispiel  
 [!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## Robuste Programmierung  
  
-   Beachten Sie, dass die folgenden Zeilen in der `Main`\-Methode auskommentiert sind, da sie Kompilierungsfehler verursachen würden.  Auf einen explizit implementierten Schnittstellenmember kann nicht über eine [Klassen](../../../csharp/language-reference/keywords/class.md)\-Instanz zugegriffen werden:  
  
     [!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   Beachten Sie auch die folgenden Zeilen in der `Main`\-Methode. Durch diese Zeilen werden die Abmessungen des Felds erfolgreich ausgegeben, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:  
  
     [!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)   
 [Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)