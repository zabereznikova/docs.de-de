---
title: "Aufrufen von Funktionen in LINQ to Entities-Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Aufrufen von Funktionen in LINQ to Entities-Abfragen
In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities\-Abfragen aufgerufen werden.  
  
 Die <xref:System.Data.Objects.EntityFunctions>\-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>\-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen.  Weitere Informationen finden Sie unter [Gewusst wie: Aufrufen von kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) und [Gewusst wie: Aufrufen von Datenbankfunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).  
  
 Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:  
  
1.  Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.  
  
2.  Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.  
  
3.  Rufen Sie die Funktion in einer LINQ to Entities\-Abfrage auf.  
  
 Weitere Informationen hierzu finden Sie in diesem Abschnitt.  
  
## In diesem Abschnitt  
 [Gewusst wie: Aufrufen von kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [Gewusst wie: Aufrufen von Datenbankfunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [Gewusst wie: Aufrufen von benutzerdefinierten Datenbankfunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [Gewusst wie: Aufrufen von vom Modell definierten Funktionen in Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [Gewusst wie: Aufrufen von modelldefinierten Funktionen als Objektmethoden](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## Siehe auch  
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [Kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)   
 [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f)