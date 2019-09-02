---
title: Hinzufügen einer "DataTable" zu einem "DataSet"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: d62d55771e4fda74d336163b3f53b3f50cfb1e39
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205291"
---
# <a name="adding-a-datatable-to-a-dataset"></a>Hinzufügen einer "DataTable" zu einem "DataSet"
Mit ADO.NET können Sie <xref:System.Data.DataTable>-Objekte erstellen und diese zu einem vorhandenen <xref:System.Data.DataSet> hinzufügen. Mit der <xref:System.Data.DataTable>-Eigenschaft und der <xref:System.Data.DataTable.PrimaryKey%2A>-Eigenschaft können Sie Einschränkungsinformationen für eine <xref:System.Data.DataColumn.Unique%2A> festlegen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Data.DataSet> erstellt und dem <xref:System.Data.DataTable> ein neues <xref:System.Data.DataSet>-Objekt hinzugefügt. Anschließend werden der Tabelle drei <xref:System.Data.DataColumn>-Objekte hinzugefügt. Zum Schluss wird durch den Code eine Spalte als Primärschlüsselspalte festgelegt.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Groß- und Kleinschreibung  
 Ein <xref:System.Data.DataSet> kann zwei oder mehr Tabellen oder Beziehungen mit demselben Namen, aber unterschiedlicher Schreibweise enthalten. In solchen Fällen muss in Verweisen auf Namen von Tabellen oder Beziehungen die Groß- und Kleinschreibung berücksichtigt werden. Wenn das **DataSet** z <xref:System.Data.DataSet> . b. die Tabellen **Table1** und **Table1**enthält, verweisen Sie auf **Table1** by Name als **DataSet. Tables ["table1"]** und **Table1** as **DataSet. Tables ["table1"]** . Wenn Sie versuchen, auf eine der Tabellen als **DataSet. Tables ["table1"]** zu verweisen, wird eine Ausnahme generiert.  
  
 Die Groß- und Kleinschreibung muss nicht berücksichtigt werden, wenn nur eine Tabelle oder Beziehung einen bestimmten Namen aufweist. Wenn <xref:System.Data.DataSet> beispielsweise nur über **Table1**verfügt, können Sie mithilfe von **DataSet. Tables ["table1"]** darauf verweisen.  
  
> [!NOTE]
> Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft des <xref:System.Data.DataSet> hat keine Auswirkungen auf dieses Verhalten. Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft gilt für die Daten im <xref:System.Data.DataSet> und hat Auswirkungen auf das Sortieren, Suchen, Filtern, Erzwingen von Einschränkungen, usw.  
  
## <a name="namespace-support"></a>Unterstützte Namespaces  
 Vor ADO.NET 2.0 konnten zwei Tabellen nicht den gleichen Namen haben, selbst wenn sie sich in unterschiedlichen Namespaces befanden. Diese Einschränkung wurde in ADO.NET 2.0 aufgehoben. Ein <xref:System.Data.DataSet> kann zwei Tabellen enthalten, die den gleichen <xref:System.Data.DataTable.TableName%2A>-Eigenschaftswert, aber unterschiedliche <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswerte aufweisen.  
  
## <a name="see-also"></a>Siehe auch

- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
