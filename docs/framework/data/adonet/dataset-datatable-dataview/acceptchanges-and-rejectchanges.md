---
title: "\"AcceptChanges\" und \"RejectChanges\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 30b2c303b1823430c480f0706500f8f7e7053c4c
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46531826"
---
# <a name="acceptchanges-and-rejectchanges"></a>"AcceptChanges" und "RejectChanges"
Nach dem Überprüfen der Genauigkeit von Änderungen an Daten in eine <xref:System.Data.DataTable>, akzeptieren Sie die Änderungen mithilfe der <xref:System.Data.DataRow.AcceptChanges%2A> Methode der <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, oder <xref:System.Data.DataSet>, festzulegen der **aktuelle** Zeile Werte der **ursprünglichen** Werte und legt die **RowState** Eigenschaft **Unchanged**. Alle löscht akzeptieren oder ablehnen von Änderungen **RowError** Informationen und legt die **HasErrors** Eigenschaft **"false"**. Das Übernehmen oder Zurückweisen von Änderungen kann sich auch auf das Update von Daten in der Datenquelle auswirken. Weitere Informationen finden Sie unter [Aktualisieren von Datenquellen mit "DataAdapters"](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Wenn foreign Key-Einschränkungen auf vorhanden sind. die **DataTable**, Änderungen akzeptiert oder abgelehnt hat, mithilfe von **AcceptChanges** und **RejectChanges** werden an die untergeordneten Zeilen der weitergegeben **DataRow** gemäß der **DataRow**. Weitere Informationen finden Sie unter [DataTable-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Im folgenden Beispiel werden Zeilen mit Fehlern gesucht, die Fehler ggf. behoben und die Zeilen, in denen die Fehler nicht behoben werden können, zurückgewiesen. Beachten Sie, dass für Fehler behobene der **RowError** Wert wird zurückgesetzt, um eine leere Zeichenfolge ist, verursacht die **HasErrors** Eigenschaft festgelegt werden, um **"false"**. Wenn alle Zeilen mit Fehlern aufgelöst oder abgelehnt wird, wurden **AcceptChanges** wird aufgerufen, um alle Änderungen für die gesamte akzeptieren **DataTable**.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
