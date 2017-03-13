---
title: "Indexer in Schnittstellen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Accessoren [C#], Indexer"
  - "Indexer [C#], In Schnittstellen"
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Indexer in Schnittstellen (C#-Programmierhandbuch)
Indexer können für [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden.  Accessoren für Schnittstellenindexer unterscheiden sich in folgenden Punkten von Accessoren für [Klassen](../../../csharp/language-reference/keywords/class.md)\-Indexer:  
  
-   Schnittstellenaccessoren verwenden keine Modifizierer.  
  
-   Ein Schnittstellenaccessor besitzt keinen Textkörper.  
  
 Ein Accessor wird also verwendet, um anzugeben, ob der Indexer Lese\- und Schreibzugriffe gleichzeitig bzw. jeweils nur Schreib\- oder Lesezugriffe unterstützt.  
  
 Das folgende Beispiel zeigt einen Accessor für einen Schnittstellenindexer:  
  
 [!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 Die Signatur eines Indexers muss sich von den Signaturen aller anderen Indexer unterscheiden, die in derselben Schnittstelle deklariert sind.  
  
## Beispiel  
 Das folgende Beispiel demonstriert die Implementierung von Schnittstellenindexern:  
  
 [!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 Um im vorangehenden Beispiel die explizite Implementierung des Schnittstellenmembers zu verwenden, geben Sie den vollqualifizierten Namen des Schnittstellenmembers an.  Beispiele:  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 Der vollqualifizierte Name wird jedoch nur benötigt, um Mehrdeutigkeiten zu vermeiden, wenn mehr als eine Schnittstelle mit der gleichen Indexersignatur von der Klasse implementiert wird.  Wenn beispielsweise die beiden Schnittstellen `ICitizen` und `IEmployee` von einer  `Employee`\-Klasse implementiert werden und beide Schnittstellen über die gleiche Indexersignatur verfügen, muss der Schnittstellenmember explizit implementiert werden.  Mit der folgenden Indexerdeklaration  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 wird der Indexer für die `IEmployee`\-Schnittstelle implementiert, während mit der Deklaration  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 der Indexer für die `ICitizen`\-Schnittstelle implementiert wird.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Schnittstellen](../../../csharp/programming-guide/interfaces/index.md)