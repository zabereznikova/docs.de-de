---
title: "\"AcceptChanges\" und \"RejectChanges\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: bbcc666b99c2bade479e5ee51750b043c820845d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879904"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="15e70-102">"AcceptChanges" und "RejectChanges"</span><span class="sxs-lookup"><span data-stu-id="15e70-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="15e70-103">Nach dem Überprüfen der Genauigkeit von Änderungen an Daten in eine <xref:System.Data.DataTable>, akzeptieren Sie die Änderungen mithilfe der <xref:System.Data.DataRow.AcceptChanges%2A> Methode der <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, oder <xref:System.Data.DataSet>, festzulegen der **aktuelle** Zeile Werte der **ursprünglichen** Werte und legt die **RowState** Eigenschaft **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="15e70-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="15e70-104">Alle löscht akzeptieren oder ablehnen von Änderungen **RowError** Informationen und legt die **HasErrors** Eigenschaft **"false"**.</span><span class="sxs-lookup"><span data-stu-id="15e70-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="15e70-105">Das Übernehmen oder Zurückweisen von Änderungen kann sich auch auf das Update von Daten in der Datenquelle auswirken.</span><span class="sxs-lookup"><span data-stu-id="15e70-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="15e70-106">Weitere Informationen finden Sie unter [Aktualisieren von Datenquellen mit "DataAdapters"](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="15e70-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="15e70-107">Wenn foreign Key-Einschränkungen auf vorhanden sind. die **DataTable**, Änderungen akzeptiert oder abgelehnt hat, mithilfe von **AcceptChanges** und **RejectChanges** werden an die untergeordneten Zeilen der weitergegeben **DataRow** gemäß der **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="15e70-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="15e70-108">Weitere Informationen finden Sie unter [DataTable-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="15e70-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="15e70-109">Im folgenden Beispiel werden Zeilen mit Fehlern gesucht, die Fehler ggf. behoben und die Zeilen, in denen die Fehler nicht behoben werden können, zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="15e70-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="15e70-110">Beachten Sie, dass für Fehler behobene der **RowError** Wert wird zurückgesetzt, um eine leere Zeichenfolge ist, verursacht die **HasErrors** Eigenschaft festgelegt werden, um **"false"**.</span><span class="sxs-lookup"><span data-stu-id="15e70-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="15e70-111">Wenn alle Zeilen mit Fehlern aufgelöst oder abgelehnt wird, wurden **AcceptChanges** wird aufgerufen, um alle Änderungen für die gesamte akzeptieren **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="15e70-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="15e70-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15e70-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="15e70-113">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="15e70-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="15e70-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="15e70-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
