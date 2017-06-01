---
title: ".NET-Leistungstipps | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "C#-Sprache, Leistung"
  - "Leistung [C#]"
  - "Leistung [Visual Basic]"
  - "Visual Basic, Leistung"
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
caps.handback.revision: 36
---
# .NET-Leistungstipps
Die Begriff *Leistung* bezieht sich im Allgemeinen auf die Ausführungsgeschwindigkeit eines Programms.  In manchen Fällen können Sie die Ausführungsgeschwindigkeit erhöhen, indem Sie im Quellcode bestimmte Grundregeln befolgen.  In einigen Programmen müssen Sie den Code genau untersuchen und mithilfe von Profilern sicherstellen, dass dieser so schnell wie möglich ausgeführt wird.  In anderen Programmen müssen Sie keine solche Optimierung ausführen, da Code in der aktuellen Form mit akzeptabler Geschwindigkeit ausgeführt wird.  Dieser Artikel beschreibt einige häufige Bereiche, in denen die Leistung abnehmen kann, und enthält Tipps zur Verbesserung sowie Links zu weiteren Leistungsthemen.  Weitere Informationen zum Planen und Messen der Leistung finden Sie unter [Performance](../../../docs/framework/performance/index.md)  
  
## Boxing und Unboxing  
 Am besten verwenden Sie keine Werttypen in Situationen, in denen sie öfter geschachtelt werden müssen, z. B. in nicht generischen Auflistungsklassen wie <xref:System.Collections.ArrayList?displayProperty=fullName>.  Sie können die Schachtelung von Werttypen vermeiden, indem Sie generische Auflistungen, z. B. <xref:System.Collections.Generic.List%601?displayProperty=fullName>, verwenden.  Boxing und Unboxing sind rechenintensive Prozesse.  Wenn ein Werttyp geschachtelt wird, muss ein völlig neues Objekt erstellt werden.  Dies kann bis zu 20\-mal länger dauern als eine einfache Zuweisung eines Verweises.  Eine Umwandlung durch Unboxing kann vier Mal mehr Zeit beanspruchen als eine Zuweisung.  Weitere Informationen finden Sie unter [Boxing und Unboxing](../Topic/Boxing%20and%20Unboxing%20\(C%23%20Programming%20Guide\).md).  
  
## Zeichenfolgen  
 Wenn Sie eine große Anzahl von Zeichenfolgenvariablen, z. B. in einer dichten Schleife, verketten, verwenden Sie <xref:System.Text.StringBuilder?displayProperty=fullName> anstelle des [\+\-Operatoren](../Topic/+%20Operator%20\(C%23%20Reference\).md) in C\# oder der [Verkettungsoperatoren](../Topic/Concatenation%20Operators%20\(Visual%20Basic\).md) in Visual Basic.  Weitere Informationen finden Sie unter [Gewusst wie: Verketten von mehreren Zeichenfolgen](../Topic/How%20to:%20Concatenate%20Multiple%20Strings%20\(C%23%20Programming%20Guide\).md) und [Concatenation Operators in Visual Basic](../Topic/Concatenation%20Operators%20in%20Visual%20Basic.md).  
  
## Destruktoren  
 Leere Destruktoren sollten nicht verwendet werden.  Wenn eine Klasse einen Destruktor enthält, wird ein Eintrag in der Finalize\-Warteschlange erstellt.  Wenn der Destruktor aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten.  Wenn der Destruktor leer ist, führt dies einfach zu einem Leistungsverlust.  Weitere Informationen finden Sie unter [Destruktoren](../Topic/Destructors%20\(C%23%20Programming%20Guide\).md) und [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md).  
  
## Weitere Ressourcen  
  
-   [Writing Faster Managed Code: Know What Things Cost](http://go.microsoft.com/fwlink/?LinkId=99294)  
  
-   [Schreiben von leistungsstarken verwalteten Anwendungen \- Ein Leitfaden](http://go.microsoft.com/fwlink/?LinkId=99295)  
  
-   [Garbage Collector\-Grundlagen und Tipps zur Leistung](http://go.microsoft.com/fwlink/?LinkId=99296)  
  
-   [Performance Tips and Tricks in .NET Applications](http://go.microsoft.com/fwlink/?LinkId=99297)  
  
-   [Einblick in die Diagnosetools für .NET](http://go.microsoft.com/fwlink/?LinkId=112407)  
  
-   [Rico Mariani's Performance Tidbits](http://go.microsoft.com/fwlink/?LinkId=115679)  
  
## Siehe auch  
 [Performance](../../../docs/framework/performance/index.md)   
 [Programmierungskonzepte](../Topic/Programming%20Concepts.md)   
 [Visual Basic Programming Guide](../Topic/Visual%20Basic%20Programming%20Guide.md)   
 [C\#\-Programmierhandbuch](../Topic/C%23%20Programming%20Guide.md)