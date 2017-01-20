---
title: "LINQ and Generic Types (C#) | Microsoft Docs"
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
  - "LINQ [C#], generic types"
  - "generic types [LINQ]"
  - "generics [LINQ]"
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# LINQ and Generic Types (C#)
[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen basieren auf generischen Typen, die in Version 2.0 von [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] eingeführt wurden.  Sie benötigen kein ausführliches Wissen über Generika, um Abfragen zu schreiben.  Dennoch ist es gut, wenn Sie zwei grundlegende Konzepte verstehen:  
  
1.  Wenn Sie eine Instanz einer generischen Auflistungsklasse erstellen, wie zum Beispiel <xref:System.Collections.Generic.List%601>, ersetzen Sie das "T" durch den Typ von Objekten, die die Liste enthalten wird.  Zum Beispiel wird eine Liste von Zeichenfolgen als `List<string>` und eine Liste von `Customer`\-Objekten als `List<Customer>` ausgedrückt.  Eine generische Liste weist eine starke Typisierung auf und bietet viele Vorteile gegenüber Auflistungen, die ihre Elemente als <xref:System.Object> speichern.  Wenn Sie versuchen, `Customer` zu `List<string>` hinzuzufügen, tritt zur Kompilierungszeit ein Fehler auf.  Die Verwendung von generischen Auflistungen ist leicht, da Sie zur Laufzeit keine Typumwandlungen ausführen müssen.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601> ist die Schnittstelle, die die Aufzählung von generischen Auflistungsklassen durch Verwenden der `foreach`\-Anweisung ermöglicht.  Generische Auflistungsklassen unterstützen <xref:System.Collections.Generic.IEnumerable%601>, ebenso wie nicht generische Auflistungsklassen, wie zum Beispiel <xref:System.Collections.ArrayList>, <xref:System.Collections.IEnumerable> unterstützen.  
  
 Weitere Informationen zu Generika finden Sie unter [Generika](../../../../csharp/programming-guide/generics/index.md).  
  
## IEnumerable\<T\>\-Variablen in LINQ\-Abfragen  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragevariablen werden als <xref:System.Collections.Generic.IEnumerable%601> typisiert oder als abgeleiteter Typ, wie zum Beispiel <xref:System.Linq.IQueryable%601>.  Wenn Sie eine Abfragevariable mit der Typisierung `IEnumerable<Customer>` sehen, so bedeutet dies lediglich, dass die Abfrage bei ihrer Ausführung eine Sequenz von keinen oder mehreren `Customer`\-Objekten erstellen wird.  
  
 [!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/GettingStarted/Class1.cs#34)]  
  
 Weitere Informationen finden Sie unter [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## Behandeln generischer Typdeklarationen mithilfe des Compilers  
 Auf Wunsch können Sie die generische Syntax auch vermeiden, indem Sie das [var](../../../../csharp/language-reference/keywords/var.md)\-Schlüsselwort verwenden.  Das `var`\-Schlüsselwort weist den Compiler an, den Typ einer Abfragevariablen abzuleiten, indem er sich nach der in der `from`\-Klausel angegebenen Datenquelle richtet.  Das folgende Beispiel erstellt den gleichen kompilierten Code wie das vorherige Beispiel:  
  
 [!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/GettingStarted/Class1.cs#35)]  
  
 Das `var`\-Schlüsselwort bietet sich besonders an, wenn der Variablentyp offensichtlich ist oder wenn die ausdrückliche Angabe von geschachtelten, generischen Typen, z. B. solche, die bei Gruppenabfragen erstellt werden, nicht so wichtig ist.  Allgemein möchten wir darauf hinweisen, dass Ihr Code durch Verwendung von `var` eventuell schlechter lesbar wird.  Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Siehe auch  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Generika](../../../../csharp/programming-guide/generics/index.md)