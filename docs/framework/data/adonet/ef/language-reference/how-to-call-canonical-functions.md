---
title: "Gewusst wie: Aufrufen von kanonischen Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Aufrufen von kanonischen Funktionen
Die <xref:System.Data.Objects.EntityFunctions>\-Klasse enthält Methoden, mit denen kanonische Funktionen in LINQ to Entities\-Abfragen verwendet werden können.  Informationen zu kanonischen Funktionen finden Sie unter [Kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).  
  
> [!NOTE]
>  Die Methoden <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> und <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> der <xref:System.Data.Objects.EntityFunctions>\-Klasse verfügen über keine kanonischen Funktionsentsprechungen.  
  
 Kanonische Funktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert \(auch bekannt als aggregierte kanonische Funktionen\) zurückgeben, können direkt aufgerufen werden.  Andere kanonische Funktionen können nur als Teil einer LINQ to Entities\-Abfrage aufgerufen werden.  Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden.  Weitere Informationen finden Sie unten im zweiten Beispiel.  
  
 Sie können einige kanonische Funktionen mit Common Language Runtime \(CLR\)\-Methoden in LINQ to Entities\-Abfragen aufrufen.  Eine Liste der CLR\-Methoden, die kanonischen Funktionen zugeordnet sind, finden Sie unter [Mapping von CLR\-Methoden zu kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
## Beispiel  
 Im folgenden Beispiel wird das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) verwendet.  Im Beispiel wird eine die <xref:System.Data.Objects.EntityFunctions.DiffDays%2A>\-Methode verwendende LINQ to Entities\-Abfrage zum Zurückgeben aller Produkte ausgeführt, für die die Differenz zwischen `SellEndDate` und `SellStartDate` weniger als 365 Tage beträgt:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## Beispiel  
 Im folgenden Beispiel wird das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) verwendet.  Im Beispiel wird die <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A>\-Aggregatmethode aufgerufen, um die Standardabweichung von `SalesOrderHeader`\-Teilergebnissen direkt zurückzugeben.  Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities\-Abfrage sein zu müssen.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## Siehe auch  
 [Aufrufen von Funktionen in LINQ to Entities\-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)   
 [Abfragen in LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)