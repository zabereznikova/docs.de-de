---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: b88df66ef2e065d1db8d4033eb1fb0e47ebdd189
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108714"
---
# <a name="creating-a-dataview"></a>Erstellen eines "DataViews"
Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>: Können Sie die **DataView** -Konstruktor verwenden, oder Sie erstellen einen Verweis auf die <xref:System.Data.DataTable.DefaultView%2A> Eigenschaft der <xref:System.Data.DataTable>. Die **DataView** Konstruktor kann leer sein oder akzeptiert entweder eine **DataTable** als einzelnes Argument, oder ein **DataTable** zusammen mit Filterkriterien, Sortierkriterien und eine Zeile State-Filter. Weitere Informationen zu zusätzlichen Argumenten, die für die Verwendung mit der **DataView**, finden Sie unter [sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Da der Index für eine **DataView** basiert sowohl bei der **DataView** erstellt wird, und wenn eine der **sortieren**, **RowFilter**, oder  **RowStateFilter** Eigenschaften geändert werden, erreichen Sie die optimale Leistung durch Angabe von alle anfänglichen Sortierreihenfolge- oder Filterkriterien als Konstruktorargumente, bei der Erstellung der **DataView**. Erstellen einer **DataView** ohne Angabe von Sortier- oder Filterkriterien festlegen und anschließend die **Sortierreihenfolge**, **RowFilter**, oder **RowStateFilter** Eigenschaften höher führt dazu, dass den Index mindestens zweimal erstellt werden sollen: nach der bei der **DataView** erstellt wird, und erneut bei Eigenschaften Sortier- oder Filtereigenschaften geändert.  
  
 Beachten Sie, dass bei der Erstellung einer **DataView** verwenden den Konstruktor, der keine Argumente akzeptiert, Sie ist nicht möglich, verwenden Sie die **DataView** bis Sie festgelegt haben die **Tabelle** Eigenschaft .  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer **DataView** mithilfe der **DataView** Konstruktor. Ein **RowFilter**, **Sortierreihenfolge** Spalte und **DataViewRowState** bereitgestellt werden, zusammen mit den **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Verweis auf den Standardwert zu erhalten **DataView** von einer **DataTable** mithilfe der **DefaultView** Eigenschaft der Tabelle.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
