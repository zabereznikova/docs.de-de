---
title: "Beispiele f&#252;r die Abfrageausdruckssyntax: Joinoperatoren (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Beispiele f&#252;r die Abfrageausdruckssyntax: Joinoperatoren (LINQ to DataSet)
Das Verknüpfen \(JOIN\) ist eine wichtige Operation bei Abfragen von Daten aus Datenquellen, bei denen es untereinander keine navigierbaren Beziehungen, wie Tabellen in relationalen Datenbanken, gibt.  Bei einer JOIN\-Operation für zwei Datenquellen werden Objekte in einer Datenquelle mit Objekten in der anderen Datenquelle, die über ein gemeinsames Attribut verfügen, miteinander verknüpft.  Weitere Informationen finden Sie unter [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.GroupJoin%2A> und <xref:System.Linq.Enumerable.Join%2A> und der Abfrageausdruckssyntax ein <xref:System.Data.DataSet> abfragen können.  
  
 Informationen zur `FillDataSet`\-Methode, die in diesen Beispielen verwendet wird, finden Sie unter [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).  
  
 In den Beispielen in diesem Thema wird auf die Tabellen \<legacyBold\>Contact\<\/legacyBold\>, \<legacyBold\>Address\<\/legacyBold\>, \<legacyBold\>Product\<\/legacyBold\>, \<legacyBold\>SalesOrderHeader\<\/legacyBold\> und \<legacyBold\>SalesOrderDetail\<\/legacyBold\> in der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank zurückgegriffen.  
  
 Die Beispiele in diesem Thema beziehen sich auf die folgenden `using`\/`Imports`\-Anweisungen:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet\-Projekts in Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).  
  
## GroupJoin  
  
### Beispiel  
 In diesem Beispiel werden die Tabellen `SalesOrderHeader` und `SalesOrderDetail` durch eine <xref:System.Linq.Enumerable.GroupJoin%2A>\-Operation miteinander verknüpft, um die Anzahl der Aufträge pro Kunde ermitteln zu können.  Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten \(linken\) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### Beispiel  
 In diesem Beispiel werden die Tabellen `Contact` und `SalesOrderHeader` mittels einer <xref:System.Linq.Enumerable.GroupJoin%2A>\-Operation miteinander verknüpft.  Eine Gruppenverknüpfung ist das Äquivalent zu einer linken äußeren Verknüpfung, die jedes Element der ersten \(linken\) Datenquelle zurückgibt, selbst wenn die andere Datenquelle keine zugehörigen Elemente enthält.  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## Join  
  
### Beispiel  
 In diesem Beispiel werden die Tabellen `SalesOrderHeader` und `SalesOrderDetail` durch eine JOIN\-Operation miteinander verknüpft, um die Onlinebestellungen für den Monat August abzurufen.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## Siehe auch  
 [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Standard Query Operators Overview](../../../../ocs/visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)