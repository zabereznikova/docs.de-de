---
title: "Hinzufügen einer \"DataTable\" zu einem \"DataSet\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f70292794866530de5b7abf7dac1edd09d300c94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="adding-a-datatable-to-a-dataset"></a>Hinzufügen einer "DataTable" zu einem "DataSet"
Mit ADO.NET können Sie <xref:System.Data.DataTable>-Objekte erstellen und diese zu einem vorhandenen <xref:System.Data.DataSet> hinzufügen. Mit der <xref:System.Data.DataTable>-Eigenschaft und der <xref:System.Data.DataTable.PrimaryKey%2A>-Eigenschaft können Sie Einschränkungsinformationen für eine <xref:System.Data.DataColumn.Unique%2A> festlegen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.DataSet> erstellt und dem <xref:System.Data.DataTable> ein neues <xref:System.Data.DataSet>-Objekt hinzugefügt. Anschließend werden der Tabelle drei <xref:System.Data.DataColumn>-Objekte hinzugefügt. Zum Schluss wird durch den Code eine Spalte als Primärschlüsselspalte festgelegt.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Groß- und Kleinschreibung  
 Ein <xref:System.Data.DataSet> kann zwei oder mehr Tabellen oder Beziehungen mit demselben Namen, aber unterschiedlicher Schreibweise enthalten. In solchen Fällen muss in Verweisen auf Namen von Tabellen oder Beziehungen die Groß- und Kleinschreibung berücksichtigt werden. Beispielsweise, wenn die <xref:System.Data.DataSet> **DataSet** enthält Tabellen **Table1** und **table1**, würden Sie verweisen **Table1** anhand des Namens **dataSet.Tables["Table1"]**, und **table1** als **dataSet.Tables["table1"]**. Versuch, auf eine der Tabellen als verweisen **dataSet.Tables["TABLE1"]** würde eine Ausnahme generiert.  
  
 Die Groß- und Kleinschreibung muss nicht berücksichtigt werden, wenn nur eine Tabelle oder Beziehung einen bestimmten Namen aufweist. Z. B. wenn die <xref:System.Data.DataSet> hat nur **Table1**, Sie können darauf verweisen **dataSet.Tables["TABLE1"]**.  
  
> [!NOTE]
>  Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft des <xref:System.Data.DataSet> hat keine Auswirkungen auf dieses Verhalten. Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft gilt für die Daten im <xref:System.Data.DataSet> und hat Auswirkungen auf das Sortieren, Suchen, Filtern, Erzwingen von Einschränkungen, usw.  
  
## <a name="namespace-support"></a>Unterstützte Namespaces  
 Vor ADO.NET 2.0 konnten zwei Tabellen nicht den gleichen Namen haben, selbst wenn sie sich in unterschiedlichen Namespaces befanden. Diese Einschränkung wurde in ADO.NET 2.0 aufgehoben. Ein <xref:System.Data.DataSet> kann zwei Tabellen enthalten, die den gleichen <xref:System.Data.DataTable.TableName%2A>-Eigenschaftswert, aber unterschiedliche <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswerte aufweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
