---
title: Sortieren und Filtern von Daten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 01c09d94fd3224e8fd875b7f6eea06b2d2c35cca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sorting-and-filtering-data"></a>Sortieren und Filtern von Daten
Die <xref:System.Data.DataView> stellt mehrere Methoden zum Sortieren und Filtern von Daten in einer <xref:System.Data.DataTable> bereit:  
  
-   Mit der <xref:System.Data.DataView.Sort%2A>-Eigenschaft können Sie einzelne oder mehrere Sortierreihenfolgen für Spalten angeben und die Parameter ASC (ascending = aufsteigend) und DESC (descending = absteigend) einfügen.  
  
-   Sie können mithilfe der <xref:System.Data.DataView.ApplyDefaultSort%2A>-Eigenschaft automatisch eine Sortierreihenfolge in aufsteigender Reihenfolge auf Grundlage der Primärschlüsselspalte bzw. -spalten der Tabelle erstellen. <xref:System.Data.DataView.ApplyDefaultSort%2A>nur gültig, wenn die **sortieren** Eigenschaft ist ein null-Verweis oder eine leere Zeichenfolge ist, und wenn die Tabelle einen Primärschlüssel definiert.  
  
-   	Mit der <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft können Sie Teilmengen von Zeilen angeben, die auf den Spaltenwerten basieren. Weitere Informationen zu gültigen Ausdrücken für die **RowFilter** -Eigenschaft, finden Sie in den Referenzinformationen für die <xref:System.Data.DataColumn.Expression%2A> Eigenschaft von der <xref:System.Data.DataColumn> Klasse.  
  
     Wunsch zurückzugeben, verwenden Sie die Ergebnisse einer bestimmten Abfrage von Daten, eine dynamische Ansicht einer Teilmenge der Daten, die <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> Methoden die **"DataView"** um optimale Leistung zu erzielen statt Festlegen der **RowFilter** Eigenschaft. Festlegen der **RowFilter** Eigenschaft erstellt den Index für die Daten, Verwaltungsmehraufwand für die Anwendung und die arbeitsgeschwindigkeit neu. Die **RowFilter** -Eigenschaft wird am besten verwendet in einer datengebundenen Anwendung ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt. Die **suchen** und **FindRows** Methoden nutzen den aktuellen Index, ohne dass der Index neu erstellt werden. Weitere Informationen zu den **suchen** und **FindRows** Methoden, finden Sie unter [Suchen nach Zeilen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   Mit der <xref:System.Data.DataView.RowStateFilter%2A>-Eigenschaft können Sie festlegen, welche Zeilenversionen Sie anzeigen möchten. Die **"DataView"** verwaltet implizit, welche Zeilenversion verfügbar machen, abhängig von der **RowState** der zugrunde liegenden Zeile. Z. B. wenn die **RowStateFilter** auf festgelegt ist **DataViewRowState.Deleted**, **"DataView"** macht die **ursprünglichen** -Zeilenversion der alle **gelöschte** Zeilen, da es ist keine **aktuelle** Zeilenversion. Können Sie bestimmen, welche Zeilenversion einer Zeile mit verfügbar gemacht wird die **RowVersion** Eigenschaft von der **DataRowView**.  
  
     Die folgende Tabelle zeigt die Optionen für **"DataViewRowState"**.  
  
    |"DataViewRowState"-Optionen|Beschreibung|  
    |------------------------------|-----------------|  
    |**CurrentRows**|Die **aktuelle** -Zeilenversion von allen **Unchanged**, **Added**, und **"geändert"** Zeilen. Dies ist die Standardeinstellung.|  
    |**Hinzugefügt**|Die **aktuelle** -Zeilenversion von allen **Added** Zeilen.|  
    |**Gelöscht**|Die **ursprünglichen** -Zeilenversion von allen **gelöschte** Zeilen.|  
    |**ModifiedCurrent**|Die **aktuelle** -Zeilenversion von allen **"geändert"** Zeilen.|  
    |**ModifiedOriginal**|Die **ursprünglichen** -Zeilenversion von allen **"geändert"** Zeilen.|  
    |**Keine**|Keine Zeilen.|  
    |**OriginalRows**|Die **ursprünglichen** -Zeilenversion von allen **Unchanged**, **"geändert"**, und **gelöschte** Zeilen.|  
    |**Unverändert**|Die **aktuelle** -Zeilenversion von allen **Unchanged** Zeilen.|  
  
 Weitere Informationen zum Zeilenstatus und Zeilenversionen finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Im folgenden Codebeispiel wird eine Ansicht erstellt, die alle Produkte anzeigt, bei denen die Anzahl der Einheiten im Lager kleiner als oder gleich der Neusortierungsebene ist, wobei zuerst nach der Lieferanten-ID und dann nach dem Produktnamen sortiert wird.  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
