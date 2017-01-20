---
title: "Anonyme Funktionen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Anonyme Funktionen [C#]"
  - "Anonyme Methoden [C#]"
  - "Lambda-Ausdrücke [C#], Als anonyme Funktionen"
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Anonyme Funktionen (C#-Programmierhandbuch)
Bei einer anonymen Funktion handelt es sich um eine "Inlineanweisung" bzw. einen Ausdruck, die bzw. der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird.  Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder sie anstelle eines benannten Delegattypen als Methodenparameter übergeben.  
  
 Es gibt zwei Arten von anonymen Funktionen, die in den folgenden Themen im Einzelnen erläutert werden:  
  
-   [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Lambda\-Ausdrücke können an Ausdrucksbaumstrukturen und an Delegaten gebunden werden.  
  
## Die Entwicklung von Delegaten in C\#  
 In C\# 1.0 wurde eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert war.  In C\# 2.0 wurde das Konzept anonymer Methoden als Möglichkeit eingeführt, unbenannte Inlineanweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können.  In C\# 3.0 wurden Lambda\-Ausdrücke eingeführt, die vom Konzept her anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind.  Diese beiden Funktionen werden allgemein als *anonyme Funktionen* bezeichnet.  Im Allgemeinen sollten Anwendungen, die mit Version 3.5 und höher von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] arbeiten, Lambda\-Ausdrücke verwenden.  
  
 Im folgenden Beispiel wird die Entwicklung der Delegaterstellung von C\# 1.0 bis C\# 3.0 veranschaulicht:  
  
 [!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/csLINQProgRef/csRef30LangFeatures_2.cs#65)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [Anweisungen, Ausdrücke und Operatoren](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)