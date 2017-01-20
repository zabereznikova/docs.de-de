---
title: "default-Schl&#252;sselwort in generischem Code (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "default-Schlüsselwort [C#], Generische Programmierung"
  - "Generika [C#], default-Schlüsselwort"
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# default-Schl&#252;sselwort in generischem Code (C#-Programmierhandbuch)
Das Zuweisen eines Standardwerts zu einem parametrisierten Typ T wird bei generischen Klassen und Methoden erschwert, wenn folgende Punkte im Voraus noch unklar sind:  
  
-   Ob T ein Referenztyp oder ein Werttyp ist.  
  
-   Wenn T ein Werttyp ist, ob es ein numerischer Wert oder eine Struktur ist.  
  
 Wenn ein parametrisierter Typ T eine Variable t hat, ist die Anweisung t \= NULL nur dann gültig, wenn T ein Referenztyp ist, und t \= 0 funktioniert nur für numerische Werttypen, nicht aber für Strukturen.  Die Lösung für dieses Problem besteht in der Verwendung des `default`\-Schlüsselworts, das NULL für Referenztypen und 0 \(null\) für numerische Werttypen zurückgibt.  Bei Strukturen werden die einzelnen Member der Struktur auf 0 \(null\) oder auf NULL initialisiert zurückgegeben – je nachdem, ob es sich um Werttypen oder Referenztypen handelt.  Bei auf NULL festlegbaren Werttypen wird standardmäßig <xref:System.Nullable%601?displayProperty=fullName> zurückgegeben; die Initialisierung erfolgt analog zu allen anderen Strukturen.  
  
 Das folgende Beispiel aus der `GenericList<T>`\-Klasse demonstriert die Verwendung des `default`\-Schlüsselworts.  Weitere Informationen finden Sie unter [Übersicht über Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-_1.cs)]  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Generika](../../../csharp/programming-guide/generics/index.md)   
 [Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Generika](../Topic/Generics%20in%20the%20.NET%20Framework.md)