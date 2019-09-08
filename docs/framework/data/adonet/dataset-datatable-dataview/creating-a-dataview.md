---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 3e1c31dac458594eee70ddd99469aca7cf63b848
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785474"
---
# <a name="creating-a-dataview"></a>Erstellen eines "DataViews"
Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>: Sie können den **DataView** -Konstruktor verwenden, oder Sie können einen Verweis auf die <xref:System.Data.DataTable.DefaultView%2A> -Eigenschaft von <xref:System.Data.DataTable>erstellen. Der **DataView** -Konstruktor kann leer sein oder entweder eine **Daten** Tabelle als einzelnes Argument oder eine **Daten** Tabelle zusammen mit Filterkriterien, Sortierkriterien und einem Zeilen Status Filter annehmen. Weitere Informationen zu den zusätzlichen Argumenten, die für die Verwendung mit **DataView**verfügbar sind, finden Sie unter [Sortieren und Filtern von Daten](sorting-and-filtering-data.md).  
  
 Da der Index für eine **DataView** sowohl bei der Erstellung der **DataView** als auch beim Ändern der Eigenschaften **Sort**, **RowFilter**oder **RowStateFilter** erstellt wird, erzielen Sie eine optimale Leistung, indem Sie alle anfänglichen Sortierreihenfolge oder Filterkriterien als Konstruktorargumente beim Erstellen der **DataView**. Wenn eine **DataView** ohne Angabe der Sortier-oder Filterkriterien erstellt und anschließend die Eigenschaften **Sort**, **RowFilter**oder **RowStateFilter** festgelegt werden, wird der Index mindestens zweimal erstellt: einmal, wenn die **DataView** erstellt und erneut, wenn eine der Sortier-oder Filtereigenschaften geändert wird.  
  
 Beachten Sie Folgendes: Wenn Sie eine **DataView** mithilfe des Konstruktors erstellen, der keine Argumente akzeptiert, können Sie die **DataView** erst verwenden, wenn Sie die **Table** -Eigenschaft festgelegt haben.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine **DataView** mit dem **DataView** -Konstruktor erstellt wird. Ein **RowFilter**, eine **Sortier** Spalte und ein **DataViewRowState** werden zusammen mit der **Daten**Tabelle bereitgestellt.  
  
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
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe der **DefaultView** -Eigenschaft der Tabelle einen Verweis auf die Standard **DataView** einer **Daten** Tabelle abrufen.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataViews](dataviews.md)
- [Sortieren und Filtern von Daten](sorting-and-filtering-data.md)
- [DataTables](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
