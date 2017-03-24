---
title: "Generika und Arrays (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#], Generika"
  - "Generika [C#], Arrays"
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Generika und Arrays (C#-Programmierhandbuch)
In C\# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 \(null\) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch.  So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können.  Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich.  Die <xref:System.Collections.Generic.IList%601>\-Schnittstelle kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen.  Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>\-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.  
  
 Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>\-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array \(in diesem Fall ein Array mit ganzen Zahlen\) durchlaufen kann.  
  
 [!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Generika](../Topic/Generics%20in%20the%20.NET%20Framework.md)