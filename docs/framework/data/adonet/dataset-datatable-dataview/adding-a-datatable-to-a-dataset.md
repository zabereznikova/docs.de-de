---
title: "Hinzuf&#252;gen einer DataTable zu einem DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Hinzuf&#252;gen einer DataTable zu einem DataSet
Mit ADO.NET können Sie <xref:System.Data.DataTable>\-Objekte erstellen und diese zu einem vorhandenen <xref:System.Data.DataSet> hinzufügen.  Mit der <xref:System.Data.DataTable.PrimaryKey%2A>\-Eigenschaft und der <xref:System.Data.DataColumn.Unique%2A>\-Eigenschaft können Sie Einschränkungsinformationen für eine <xref:System.Data.DataTable> festlegen.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.DataSet> erstellt und dem <xref:System.Data.DataSet> ein neues <xref:System.Data.DataTable>\-Objekt hinzugefügt. Anschließend werden der Tabelle drei <xref:System.Data.DataColumn>\-Objekte hinzugefügt.  Zum Schluss wird durch den Code eine Spalte als Primärschlüsselspalte festgelegt.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## Groß\- und Kleinschreibung  
 Ein <xref:System.Data.DataSet> kann zwei oder mehr Tabellen oder Beziehungen mit demselben Namen, aber unterschiedlicher Schreibweise enthalten.  In solchen Fällen muss in Verweisen auf Namen von Tabellen oder Beziehungen die Groß\- und Kleinschreibung berücksichtigt werden.  Wenn beispielsweise das <xref:System.Data.DataSet> **dataSet** die Tabellen **Table1** und **table1** enthält, muss auf den Namen von **Table1** mit **dataSet.Tables\["Table1"\]** verwiesen werden, und auf den Namen von **table1** mit **dataSet.Tables\["table1"\]**.  Wenn Sie auf eine der Tabellen als **dataSet.Tables\["TABLE1"\]** verweisen, wird eine Ausnahme ausgelöst.  
  
 Die Groß\- und Kleinschreibung muss nicht berücksichtigt werden, wenn nur eine Tabelle oder Beziehung einen bestimmten Namen aufweist.  Wenn beispielsweise das <xref:System.Data.DataSet> nur **Table1** enthält, können Sie mit **dataSet.Tables\["TABLE1"\]** auf die Tabelle verweisen.  
  
> [!NOTE]
>  Die <xref:System.Data.DataSet.CaseSensitive%2A>\-Eigenschaft des <xref:System.Data.DataSet> hat keine Auswirkungen auf dieses Verhalten.  Die <xref:System.Data.DataSet.CaseSensitive%2A>\-Eigenschaft gilt für die Daten im <xref:System.Data.DataSet> und hat Auswirkungen auf das Sortieren, Suchen, Filtern, Erzwingen von Einschränkungen, usw.  
  
## Unterstützte Namespaces  
 Vor ADO.NET 2.0 konnten zwei Tabellen nicht den gleichen Namen haben, selbst wenn sie sich in unterschiedlichen Namespaces befanden.  Diese Einschränkung wurde in ADO.NET 2.0 aufgehoben.  Ein <xref:System.Data.DataSet> kann zwei Tabellen enthalten, die den gleichen <xref:System.Data.DataTable.TableName%2A>\-Eigenschaftswert, aber unterschiedliche <xref:System.Data.DataTable.Namespace%2A>\-Eigenschaftswerte aufweisen.  
  
## Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)