---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 539e9763c8aa4affdb6f3bd219a99dbca50cee01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202342"
---
# <a name="creating-a-dataview"></a>Erstellen eines "DataViews"

Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>: Sie können den **DataView** -Konstruktor verwenden, oder Sie können einen Verweis auf die- <xref:System.Data.DataTable.DefaultView%2A> Eigenschaft von erstellen <xref:System.Data.DataTable> . Der **DataView** -Konstruktor kann leer sein oder entweder eine **Daten** Tabelle als einzelnes Argument oder eine **Daten** Tabelle zusammen mit Filterkriterien, Sortierkriterien und einem Zeilen Status Filter annehmen. Weitere Informationen zu den zusätzlichen Argumenten, die für die Verwendung mit **DataView**verfügbar sind, finden Sie unter [Sortieren und Filtern von Daten](sorting-and-filtering-data.md).  
  
 Da der Index für eine **DataView** sowohl bei der Erstellung der **DataView** als auch bei einer Änderung der Eigenschaften **Sort**, **RowFilter**oder **RowStateFilter** erstellt wird, erzielen Sie eine optimale Leistung, indem Sie beim Erstellen der **DataView**eine beliebige anfängliche Sortierreihenfolge oder Filterkriterien als Konstruktorargumente angeben. Wenn Sie eine **DataView** ohne Angabe von Sortier-oder Filterkriterien erstellen und dann die Eigenschaften **Sort**, **RowFilter**oder **RowStateFilter** später festlegen, wird der Index mindestens zweimal erstellt: einmal, wenn die **DataView** erstellt wird, und auch dann, wenn eine der Sortier-oder Filtereigenschaften geändert wird.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- ["DataViews"](dataviews.md)
- [Sortieren und Filtern von Daten](sorting-and-filtering-data.md)
- ["DataTables"](datatables.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
