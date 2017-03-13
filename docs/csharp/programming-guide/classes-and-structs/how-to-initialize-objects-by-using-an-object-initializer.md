---
title: "Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Objektinitialisierer [C#], Verwendung"
  - "Objekte [C#], Initialisieren"
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)
Mit Objektinitialisierern können Sie Typobjekte deklarativ initialisieren, ohne den Konstruktor für den Typ explizit aufzurufen.  
  
 In den folgenden Beispielen wird gezeigt, wie Objektinitialisierer mit benannten Objekten verwendet werden.  Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzkonstruktor zugreift und dann die Memberinitialisierungen verarbeitet.  Daher schlagen Objektinitialisierer, die öffentlichen Zugriff erfordern, fehl, wenn der Standardkonstruktor in der Klasse als `private` deklariert ist.  
  
 Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.  Weitere Informationen finden Sie unter [Gewusst wie: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein neuer `StudentName`\-Typ mit einem Objektinitialisierer initialisiert wird.  
  
 [!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine Auflistung von `StudentName`\-Typen mit einem Auflistungsinitialisierer initialisiert wird.  Beachten Sie, dass ein Auflistungsinitialisierer aus einer Reihe von durch Trennzeichen getrennten Objektinitialisierern besteht.  
  
 [!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## Kompilieren des Codes  
 Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C\#\-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] erstellt wurde.  Weitere Informationen finden Sie unter [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)