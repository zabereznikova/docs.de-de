---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151337"
---
# <a name="creating-a-dataview"></a>Erstellen eines "DataViews"
Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>: Sie können den **DataView-Konstruktor** verwenden oder einen <xref:System.Data.DataTable.DefaultView%2A> Verweis <xref:System.Data.DataTable>auf die Eigenschaft der erstellen. Der **DataView-Konstruktor** kann leer sein, oder er kann entweder eine **DataTable** als einzelnes Argument oder eine **DataTable** zusammen mit Filterkriterien, Sortierkriterien und einem Zeilenstatusfilter verwenden. Weitere Informationen zu den zusätzlichen Argumenten, die für die Verwendung mit **DataView**verfügbar sind, finden Sie unter [Sortieren und Filtern von Daten](sorting-and-filtering-data.md).  
  
 Da der Index für eine **DataView** sowohl beim Erstellen der **DataView** als auch beim Ändern der **Eigenschaften Sort**, **RowFilter**oder **RowStateFilter** erstellt wird, erzielen Sie die beste Leistung, indem Sie beim Erstellen der **DataView**alle anfänglichen Sortierreihenfolge- oder Filterkriterien als Konstruktorargumente angeben. Das Erstellen einer **DataView** ohne Angabe von Sortier- oder Filterkriterien und anschließendes Festlegen der **Eigenschaften Sortieren**, **RowFilter**oder **RowStateFilter** bewirkt, dass der Index mindestens zweimal erstellt wird: einmal, wenn die **DataView** erstellt wird, und erneut, wenn die Sortier- oder Filtereigenschaften geändert werden.  
  
 Beachten Sie, dass Sie, wenn Sie eine **DataView** mit dem Konstruktor erstellen, der keine Argumente verwendet, die **DataView** erst verwenden können, wenn Sie die **Table-Eigenschaft** festgelegt haben.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine **DataView** mit dem **DataView-Konstruktor** erstellen. Eine **RowFilter**-, **Sortierspalte** und **DataViewRowState** werden zusammen mit der **DataTable**bereitgestellt.  
  
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
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe der **DefaultView-Eigenschaft** der Tabelle einen Verweis auf die **Standarddatenansicht** einer **DataTable** abrufen.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- ["DataViews"](dataviews.md)
- [Sortieren und Filtern von Daten](sorting-and-filtering-data.md)
- ["DataTables"](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
