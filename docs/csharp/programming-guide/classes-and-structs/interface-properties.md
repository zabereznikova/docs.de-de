---
title: "Schnittstelleneigenschaften (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Schnittstellen [C#], Eigenschaften"
  - "Eigenschaften [C#], Auf Schnittstellen"
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Schnittstelleneigenschaften (C#-Programmierhandbuch)
Eigenschaften können für [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden.  Das folgende Beispiel zeigt einen Accessor für einen Schnittstellenindexer:  
  
 [!code-cs[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_1.cs)]  
  
 Der Accessor einer Schnittstelleneigenschaft enthält keinen Text.  Ein Accessor wird also verwendet, um anzugeben, ob die Eigenschaft Lese\- und Schreibzugriffe gleichzeitig bzw. jeweils nur Schreib\- oder Lesezugriffe unterstützt.  
  
## Beispiel  
 In diesem Beispiel hat die `IEmployee`\-Schnittstelle eine Lesen\-\/Schreiben\-Eigenschaft `Name` und eine Nur\-Schreiben\-Eigenschaft `Counter`.  Die `Employee`\-Klasse implementiert die `IEmployee`\-Schnittstelle und verwendet diese beiden Eigenschaften.  Der Name eines neuen Mitarbeiters und die aktuelle Anzahl der Mitarbeiter werden vom Programm gelesen, und der Mitarbeitername sowie die berechnete Anzahl von Mitarbeitern wird angezeigt.  
  
 Sie könnten den vollqualifizierten Namen der Eigenschaft verwenden, die auf die Schnittstelle verweist, in der der Member deklariert ist.  Beispiele:  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_2.cs)]  
  
 Dies wird als [Explizite Schnittstellenimplementierung](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) bezeichnet.  Wenn beispielsweise zwei Schnittstellen, `ICitizen` und `IEmployee`, von der `Employee`\-Klasse implementiert sind und beide Schnittstellen über die `Name`\-Eigenschaft verfügen, muss der Schnittstellenmember explizit implementiert werden.  Mit der folgenden Eigenschaftendeklaration  
  
 [!code-cs[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_2.cs)]  
  
 wird die `Name`\-Eigenschaft für die `IEmployee`\-Schnittstelle implementiert, während mit der Deklaration  
  
 [!code-cs[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_3.cs)]  
  
 die `Name`\-Eigenschaft für die `ICitizen`\-Schnittstelle implementiert wird.  
  
 [!code-cs[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## Beispielausgabe  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Verwenden von Eigenschaften](../../../csharp/programming-guide/classes-and-structs/using-properties.md)   
 [Vergleich zwischen Eigenschaften und Indexern](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)