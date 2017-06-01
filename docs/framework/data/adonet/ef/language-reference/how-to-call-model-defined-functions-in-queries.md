---
title: "Gewusst wie: Aufrufen von vom Modell definierten Funktionen in Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Aufrufen von vom Modell definierten Funktionen in Abfragen
In diesem Thema wird beschrieben, wie Funktionen, die im konzeptionellen Modell definiert sind, aus [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen heraus aufgerufen werden.  
  
 Das nachfolgende Verfahren bietet einen allgemeinen Überblick über den Aufruf einer im Modell definierten Funktion aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfrage heraus.  Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur.  In dem Verfahren wird davon ausgegangen, dass eine Funktion im konzeptionellen Modell definiert wurde.  Weitere Informationen finden Sie unter [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
### So rufen Sie eine im konzeptionellen Modell definierte Funktion auf  
  
1.  Fügen Sie der Anwendung, die der im konzeptionellen Modell definierten Funktion zugeordnet ist, eine Common Language Runtime \(CLR\)\-Methode hinzu.  Zum Zuordnen der Methode müssen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode übernehmen.  Beachten Sie, dass der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>\-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>\-Parameter des Attributs den Namespacenamen bzw. den Funktionsnamen im konzeptionellen Modell darstellen.  Bei der Funktionsnamenauflösung für LINQ wird die Groß\-\/Kleinschreibung berücksichtigt.  
  
2.  Rufen Sie die Funktion in einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfrage auf.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Funktion, die im konzeptionellen Modell definiert wird, aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfrage heraus aufgerufen wird.  Im Beispiel wird das Modell "School" verwendet.  Weitere Informationen zum Modell "School" finden Sie unter [Creating the School Sample Database](http://msdn.microsoft.com/de-de/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) und [Generating the School .edmx File](http://msdn.microsoft.com/de-de/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 Die folgende konzeptionelle Modellfunktion gibt die Anzahl der Jahre zurück, die seit der Einstellung einer Lehrkraft vergangen sind.  Informationen zum Hinzufügen der Funktion zu einem konzeptionellen Modell finden Sie unter [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/de-de/0dad7b8b-58f6-4271-b238-f34810d68e5f).  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
 <!-- TODO: review snippet reference [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/obj/debug/edmxresourcestoembed/school.csdl#1)]  -->  
  
## Beispiel  
 Fügen Sie der Anwendung danach die folgende Methode hinzu, und verwenden Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>, um sie der Funktion im konzeptionellen Modell zuzuordnen:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## Beispiel  
 Jetzt können Sie die im konzeptionellen Modell definierte Funktion aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfrage heraus aufrufen.  Im folgenden Code wird die Methode aufgerufen, um alle Lehrkräfte anzuzeigen, die vor mehr als zehn Jahren eingestellt wurden:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## Siehe auch  
 [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)   
 [Aufrufen von Funktionen in LINQ to Entities\-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Gewusst wie: Aufrufen von modelldefinierten Funktionen als Objektmethoden](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)