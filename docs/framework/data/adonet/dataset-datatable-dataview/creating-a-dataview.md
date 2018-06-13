---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: d118f97e425782dbdf89c7e5d1eccd4d371b419c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759113"
---
# <a name="creating-a-dataview"></a>Erstellen eines "DataViews"
Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>: Können Sie die **"DataView"** -Konstruktor verwenden, oder Sie erstellen einen Verweis auf die <xref:System.Data.DataTable.DefaultView%2A> Eigenschaft von der <xref:System.Data.DataTable>. Die **"DataView"** Konstruktor kann leer sein oder akzeptiert entweder eine **DataTable** als ein einzelnes Argument oder eine **DataTable** zusammen mit Filterkriterien, Sortierkriterien und eine Zeile Statusfilter. Weitere Informationen über die zusätzlichen Argumente für die Verwendung mit der **"DataView"**, finden Sie unter [sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Da der Index für eine **"DataView"** basiert sowohl bei der **"DataView"** erstellt wurde, und wenn Änderungen an der **sortieren**, **RowFilter**, oder  **RowStateFilter** Eigenschaften geändert werden, Sie optimale Leistung erzielen, indem Angabe alle anfänglichen Sortierreihenfolge- oder Filterkriterien als Konstruktorargumente, bei der Erstellung der **"DataView"**. Erstellen einer **"DataView"** ohne Sortier- oder Filterkriterien angeben sowie das anschließende Festlegen der **sortieren**, **RowFilter**, oder **RowStateFilter** Eigenschaften höher führt dazu, dass den Index mindestens zweimal erstellt werden sollen: Sobald bei der **"DataView"** erstellt wurde, und erneut Wenn eine der Sortier- oder Filtereigenschaften geändert.  
  
 Beachten Sie, dass bei der Erstellung einer **"DataView"** mithilfe des Konstruktors, der keine Argumente akzeptiert, Sie ist nicht möglich, verwenden Sie die **"DataView"** , bis Sie festgelegt haben die **Tabelle** Eigenschaft .  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer **"DataView"** mithilfe der **DataView** Konstruktor. Ein **RowFilter**, **sortieren** Spalte und **"DataViewRowState"** bereitgestellt werden, zusammen mit den **DataTable**.  
  
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
  
 Im folgenden Codebeispiel wird veranschaulicht, wie einen Verweis auf den Standardwert abgerufen **"DataView"** von einer **DataTable** mithilfe der **DefaultView** -Eigenschaft der Tabelle.  
  
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
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
