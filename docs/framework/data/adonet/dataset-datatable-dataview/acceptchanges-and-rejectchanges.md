---
title: "&#39;AcceptChanges&#39; und &#39;RejectChanges&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# &#39;AcceptChanges&#39; und &#39;RejectChanges&#39;
Nach Sie sichergestellt haben, dass die Änderungen an den Daten in einer <xref:System.Data.DataTable> korrekt sind, können Sie die Änderungen mithilfe der <xref:System.Data.DataRow.AcceptChanges%2A>\-Methode der <xref:System.Data.DataRow>, der <xref:System.Data.DataTable> oder des <xref:System.Data.DataSet> übernehmen. Dadurch werden die **Current**\-Zeilenwerte auf **Original**\-Werte festgelegt, und die **RowState**\-Eigenschaft wird auf **Unchanged** festgelegt.  Durch Übernehmen oder Ablehnen der Änderungen werden jegliche **RowError**\-Informationen gelöscht, und die **HasErrors** Eigenschaft wird auf **false** festgelegt.  Das Übernehmen oder Zurückweisen von Änderungen kann sich auch auf das Update von Daten in der Datenquelle auswirken.  Weitere Informationen finden Sie unter [Aktualisieren von Datenquellen mit DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Wenn für die **DataTable** Fremdschlüsseleinschränkungen vorhanden sind, werden Änderungen, die mit **AcceptChanges** und **RejectChanges** übernommen oder zurückgewiesen wurden, gemäß der **ForeignKeyConstraint.AcceptRejectRule** an die untergeordneten Zeilen der **DataRow** weitergegeben.  Weitere Informationen finden Sie unter ['DataTable'\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Im folgenden Beispiel werden Zeilen mit Fehlern gesucht, die Fehler ggf. behoben und die Zeilen, in denen die Fehler nicht behoben werden können, zurückgewiesen.  Beachten Sie, dass der **RowError**\-Wert für behobene Fehler auf eine leere Zeichenfolge zurückgesetzt wird, was dazu führt, dass für die **HasErrors**\-Eigenschaft **false** festgelegt wird.  Wenn alle Zeilen mit Fehlern aufgelöst oder zurückgewiesen wurden, wird **AcceptChanges** aufgerufen, um alle Änderungen für die gesamte **DataTable** zu übernehmen.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## Siehe auch  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)