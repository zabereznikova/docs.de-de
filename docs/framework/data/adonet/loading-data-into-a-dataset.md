---
title: "Laden von Daten in ein &#39;DataSet&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Laden von Daten in ein &#39;DataSet&#39;
Ein <xref:System.Data.DataSet>\-Objekt muss zuerst aufgefüllt werden, bevor Sie es mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] abfragen können.  Das Auffüllen des <xref:System.Data.DataSet>\-Objekts kann auf verschiedene Art und Weise erfolgen.  So können Sie z. B. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] verwenden, um die Datenbank abzufragen und die Ergebnisse in das <xref:System.Data.DataSet> zu laden.  Weitere Informationen finden Sie unter [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 Eine andere Möglichkeit, Daten in ein <xref:System.Data.DataSet> zu laden, besteht darin, Daten mithilfe der <xref:System.Data.Common.DataAdapter>\-Klasse aus der Datenbank abzurufen.  Dies wird im folgenden Beispiel illustriert.  
  
## Beispiel  
 In diesem Beispiel wird ein <xref:System.Data.Common.DataAdapter> verwendet, um aus der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Datenbank Verkaufsinformationen für das Jahr 2002 abzurufen und die Ergebnisse in ein <xref:System.Data.DataSet> zu laden.  Nachdem das <xref:System.Data.DataSet> aufgefüllt wurde, können Sie mithilfe von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen Daten aus ihm abrufen.  Die in diesem Beispiel verwendete `FillDataSet`\-Methode kommt in den Beispielabfragen in [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md) zum Einsatz.  Weitere Informationen finden Sie unter [Abfragen von 'DataSets'](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## Siehe auch  
 [Übersicht über LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)   
 [Abfragen von 'DataSets'](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)