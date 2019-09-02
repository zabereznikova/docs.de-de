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
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="ab8b8-102">"AcceptChanges" und "RejectChanges"</span><span class="sxs-lookup"><span data-stu-id="ab8b8-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="ab8b8-103">Nachdem Sie die Richtigkeit der Änderungen an den Daten in einem <xref:System.Data.DataTable>überprüft haben, können Sie die Änderungen mithilfe <xref:System.Data.DataRow.AcceptChanges%2A> der-Methode <xref:System.Data.DataRow>von <xref:System.Data.DataTable>, oder <xref:System.Data.DataSet>übernehmen, die die **aktuellen** Zeilen Werte **als Ursprüngliche** Werte und legen die **RowState** -Eigenschaft auf " **unverändert**" fest.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="ab8b8-104">Durch das akzeptieren oder ablehnen von Änderungen werden alle **RowError** -Informationen gelöscht, und die **HasErrors** -Eigenschaft wird auf **false**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="ab8b8-105">Das Übernehmen oder Zurückweisen von Änderungen kann sich auch auf das Update von Daten in der Datenquelle auswirken.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="ab8b8-106">Weitere Informationen finden Sie unter [Aktualisieren von Datenquellen mit DataAdapters](../updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="ab8b8-106">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="ab8b8-107">Wenn für die **Daten**Tabelle Foreign Key-Einschränkungen vorhanden sind, werden mithilfe von " **Accept Changes** " und " **RejectChanges** " akzeptierte oder abgelehnte Änderungen an die untergeordneten Zeilen der **DataRow** entsprechend der  **Fremdschlüssel Einschränkung. Accept trejectrule**.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="ab8b8-108">Weitere Informationen finden Sie unter [databel-Einschränkungen](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="ab8b8-108">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="ab8b8-109">Im folgenden Beispiel werden Zeilen mit Fehlern gesucht, die Fehler ggf. behoben und die Zeilen, in denen die Fehler nicht behoben werden können, zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="ab8b8-110">Beachten Sie, dass bei aufgelösten Fehlern der **RowError** -Wert auf eine leere Zeichenfolge zurückgesetzt wird, wodurch die **HasErrors** -Eigenschaft auf **false**festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="ab8b8-111">Wenn alle Zeilen mit Fehlern aufgelöst oder abgelehnt wurden, wird " **Accept Changes** " aufgerufen, um alle Änderungen für die gesamte **Daten**Tabelle zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="ab8b8-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab8b8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab8b8-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ab8b8-113">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="ab8b8-113">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="ab8b8-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ab8b8-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
