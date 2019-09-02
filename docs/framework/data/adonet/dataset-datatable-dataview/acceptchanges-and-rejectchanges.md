---
title: "\"AcceptChanges\" und \"RejectChanges\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: a8589b157bc2579a03d856b73802abc9a4b42855
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204076"
---
# <a name="acceptchanges-and-rejectchanges"></a>"AcceptChanges" und "RejectChanges"
Nachdem Sie die Richtigkeit der Änderungen an den Daten in einem <xref:System.Data.DataTable>überprüft haben, können Sie die Änderungen mithilfe <xref:System.Data.DataRow.AcceptChanges%2A> der-Methode <xref:System.Data.DataRow>von <xref:System.Data.DataTable>, oder <xref:System.Data.DataSet>übernehmen, die die **aktuellen** Zeilen Werte **als Ursprüngliche** Werte und legen die **RowState** -Eigenschaft auf " **unverändert**" fest. Durch das akzeptieren oder ablehnen von Änderungen werden alle **RowError** -Informationen gelöscht, und die **HasErrors** -Eigenschaft wird auf **false**festgelegt. Das Übernehmen oder Zurückweisen von Änderungen kann sich auch auf das Update von Daten in der Datenquelle auswirken. Weitere Informationen finden Sie unter [Aktualisieren von Datenquellen mit DataAdapters](../updating-data-sources-with-dataadapters.md).  
  
 Wenn für die **Daten**Tabelle Foreign Key-Einschränkungen vorhanden sind, werden mithilfe von " **Accept Changes** " und " **RejectChanges** " akzeptierte oder abgelehnte Änderungen an die untergeordneten Zeilen der **DataRow** entsprechend der  **Fremdschlüssel Einschränkung. Accept trejectrule**. Weitere Informationen finden Sie unter [databel-Einschränkungen](datatable-constraints.md).  
  
 Im folgenden Beispiel werden Zeilen mit Fehlern gesucht, die Fehler ggf. behoben und die Zeilen, in denen die Fehler nicht behoben werden können, zurückgewiesen. Beachten Sie, dass bei aufgelösten Fehlern der **RowError** -Wert auf eine leere Zeichenfolge zurückgesetzt wird, wodurch die **HasErrors** -Eigenschaft auf **false**festgelegt wird. Wenn alle Zeilen mit Fehlern aufgelöst oder abgelehnt wurden, wird " **Accept Changes** " aufgerufen, um alle Änderungen für die gesamte **Daten**Tabelle zu akzeptieren.  
  
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

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Bearbeiten von Daten in einer DataTable](manipulating-data-in-a-datatable.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
