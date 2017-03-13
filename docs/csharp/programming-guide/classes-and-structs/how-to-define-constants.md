---
title: "Gewusst wie: Definieren von Konstanten in C# | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Konstanten"
  - "Konstanten [C#]"
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# Gewusst wie: Definieren von Konstanten in C# #
Konstanten sind Felder, deren Werte bei der Kompilierung festgelegt werden und nie geändert werden können.  Verwenden Sie Konstanten, um aussagekräftige Namen anstelle von numerischen Literalen \("Magic\-Nummern"\) für spezielle Werte anzugeben.  
  
> [!NOTE]
>  In C\# kann die [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)\-Präprozessordirektive nicht zum Definieren von Konstanten verwendet werden, wie es bei C und C\+\+ üblich ist.  
  
 Um konstante Werte von Ganzzahltypen \(`int`, `byte` usw.\) zu definieren, verwenden Sie einen Enumerationstyp.  Weitere Informationen finden Sie unter [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Um nicht\-ganzzahlige Konstanten zu definieren, können Sie sie beispielsweise in einer einzelnen statischen Klasse mit dem Namen `Constants` gruppieren.  Dafür muss allen Verweisen auf die Konstanten der Klassenname vorangestellt werden, wie im folgenden Beispiel gezeigt wird.  
  
## Beispiel  
 [!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 Die Verwendung des Klassennamenqualifizierers stellt sicher, dass Sie und andere, die die Konstante verwenden, erkennen, dass es sich um eine Konstante handelt, die somit nicht geändert werden kann.  
  
## Siehe auch  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)