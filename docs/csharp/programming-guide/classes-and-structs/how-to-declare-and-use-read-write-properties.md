---
title: "Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "get-Accessor [C#], Deklarieren von Eigenschaften"
  - "Set-Accessor [C#]"
  - "Eigenschaften [C#], deklarieren"
  - "Lese-/Schreibeigenschaften [C#]"
  - "Accessoren [C#], Deklarieren von Eigenschaften mit"
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Deklarieren und Verwenden von Lese-/Schreibeigenschaften (C#-Programmierhandbuch)
Eigenschaften stellen die Vorteile von öffentlichen Datenmembern bereit, ohne die mit dem ungeschützten, nicht kontrollierten und nicht geprüften Zugriff auf die Daten eines Objekts verknüpften Risiken aufzuweisen.  Dies wird durch *Accessoren* erreicht. Dies sind besondere Methoden, die den zugrunde liegenden Datenmembern Werte zuweisen bzw. diese Werte abrufen.  Der [set](../../../csharp/language-reference/keywords/set.md)\-Accessor ermöglicht das Zuweisen von Datenmembern, und der [get](../../../csharp/language-reference/keywords/get.md)\-Accessor ruft Datenmemberwerte ab.  
  
 In diesem Beispiel wird eine `Person`\-Klasse mit zwei Eigenschaften dargestellt: `Name` \(Zeichenfolge\) und `Age` \(ganze Zahl\).  Beide Eigenschaften stellen einen `get`\-Accessor und einen `set`\-Accessor bereit, es handelt sich also um Lese\-\/Schreibeigenschaften.  
  
## Beispiel  
 [!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read_1.cs)]  
  
## Robuste Programmierung  
 Im vorherigen Beispiel sind die `Name`\-Eigenschaft und die `Age`\-Eigenschaft [public](../../../csharp/language-reference/keywords/public.md) und besitzen jeweils einen `get`\-Accessor und einen `set`\-Accessor.  Auf diese Weise können diese Eigenschaften von allen Objekten gelesen und überschrieben werden.  Bisweilen ist es jedoch auch erforderlich, einen der Accessoren auszuschließen.  Indem Sie den `set`\-Accessor auslassen, wandeln Sie die Eigenschaft beispielsweise in eine schreibgeschützte Eigenschaft um:  
  
 [!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read_2.cs)]  
  
 Alternativ können Sie einen Accessor öffentlich verfügbar machen, während der andere als privat oder geschützt festgelegt wird.  Weitere Informationen finden Sie unter [Asymmetrischer Accessorzugriff](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
 Nachdem die Eigenschaften deklariert wurden, können Sie genauso wie Felder der Klasse verwendet werden.  Daher kann sowohl beim Abrufen als auch beim Festlegen von Eigenschaftswerten eine relativ natürliche Syntax verwendet werden. Siehe dazu folgende Anweisungen:  
  
 [!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read_3.cs)]  
  
 Beachten Sie, dass in der `set`\-Methode einer Eigenschaft eine spezielle `value`\-Variable verfügbar ist.  Diese Variable enthält den vom Benutzer angegebenen Wert. Beispiel:  
  
 [!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read_4.cs)]  
  
 Beachten Sie die einfache Syntax zum Erhöhen des `Age`\-Eigenschaftswerts eines `Person`\-Objekts:  
  
 [!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read_5.cs)]  
  
 Wenn getrennte `set`\-Methoden und `get`\-Methoden verwendet wurden, um Eigenschaften zu modellieren, könnte der entsprechende Code folgendermaßen aussehen:  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 Die `ToString`\-Methode wird in diesem Beispiel überschrieben:  
  
 [!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read_6.cs)]  
  
 Beachten Sie, dass `ToString` im Programm nicht explizit verwendet wird.  Es wird standardmäßig durch die `WriteLine`\-Aufrufe aufgerufen.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)