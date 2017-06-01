---
title: "Ausdr&#252;cke in LINQ to Entities-Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ausdr&#252;cke in LINQ to Entities-Abfragen
Ein Ausdruck ist ein Codefragment, das als einzelner Wert, einzelnes Objekt, einzelne Methode oder einzelner Namespace ausgewertet werden kann.  Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen einfachen Namen enthalten.  Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein.  Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen.  Die Bandbreite der möglichen Ausdrücke reicht daher von einfach bis sehr komplex.  
  
 In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen können Ausdrücke alle im <xref:System.Linq.Expressions>\-Namespace zulässigen Typen enthalten, einschließlich Lambda\-Ausdrücke.  Die Ausdrücke, die in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen verwendet werden können, umfassen die Ausdrücke, mit denen das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] abgefragt werden kann.  Ausdrücke, die Teil einer Abfrage des [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind, sind auf Operationen eingeschränkt, die von `ObjectQuery<T>` und der zugrunde liegenden Datenquelle unterstützt werden.  
  
 Im folgenden Beispiel ist der Vergleich in der `Where`\-Klausel ein Ausdruck:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  Bestimmte Sprachkonstrukte, wie `unchecked` in C\#, haben in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] keine Bedeutung.  
  
## In diesem Abschnitt  
 [Konstante Ausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Vergleichsausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [NULL\-Vergleiche](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Initialisierungsausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Navigation Properties](http://msdn.microsoft.com/de-de/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## Siehe auch  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)