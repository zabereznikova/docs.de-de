---
title: Sortieren und Filtern von Daten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 0907aa2a66e1bf51fefc7bed8ea2612cc0c830fa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203215"
---
# <a name="sorting-and-filtering-data"></a>Sortieren und Filtern von Daten
Die <xref:System.Data.DataView> stellt mehrere Methoden zum Sortieren und Filtern von Daten in einer <xref:System.Data.DataTable> bereit:  
  
- Mit der <xref:System.Data.DataView.Sort%2A>-Eigenschaft können Sie einzelne oder mehrere Sortierreihenfolgen für Spalten angeben und die Parameter ASC (ascending = aufsteigend) und DESC (descending = absteigend) einfügen.  
  
- Sie können mithilfe der <xref:System.Data.DataView.ApplyDefaultSort%2A>-Eigenschaft automatisch eine Sortierreihenfolge in aufsteigender Reihenfolge auf Grundlage der Primärschlüsselspalte bzw. -spalten der Tabelle erstellen. <xref:System.Data.DataView.ApplyDefaultSort%2A>gilt nur, wenn die **Sort** -Eigenschaft ein NULL-Verweis oder eine leere Zeichenfolge ist und wenn für die Tabelle ein Primärschlüssel definiert ist.  
  
- Mit der <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft können Sie Teilmengen von Zeilen angeben, die auf den Spaltenwerten basieren. Ausführliche Informationen zu gültigen Ausdrücken für die **RowFilter** -Eigenschaft finden Sie in den Referenzinformationen <xref:System.Data.DataColumn.Expression%2A> für die- <xref:System.Data.DataColumn> Eigenschaft der-Klasse.  
  
     Wenn Sie die Ergebnisse einer bestimmten Abfrage für die Daten zurückgeben möchten, anstatt eine dynamische Ansicht einer Teilmenge der Daten bereitzustellen, verwenden Sie die <xref:System.Data.DataView.Find%2A> -Methode oder <xref:System.Data.DataView.FindRows%2A> die-Methode der **DataView** , um eine optimale Leistung zu erzielen, anstatt das  **RowFilter** -Eigenschaft. Wenn Sie die **RowFilter** -Eigenschaft festlegen, wird der Index für die Daten neu erstellt, und die Leistung wird erhöht, und die Leistung wird verringert. Die **RowFilter** -Eigenschaft wird am besten in einer Daten gebundenen Anwendung verwendet, in der ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt. Die **Find** -Methode und die **FindRows** -Methode nutzen den aktuellen Index, ohne dass der Index neu erstellt werden muss. Weitere Informationen zu den Methoden **Find** und **FindRows** finden Sie untersuchen von [Zeilen](finding-rows.md).  
  
- Mit der <xref:System.Data.DataView.RowStateFilter%2A>-Eigenschaft können Sie festlegen, welche Zeilenversionen Sie anzeigen möchten. Die **DataView** verwaltet implizit, welche Zeilen Version in Abhängigkeit vom **RowState** der zugrunde liegenden Zeile verfügbar gemacht werden soll. Wenn z. b. **RowStateFilter** auf **DataViewRowState. Deleted**festgelegt ist, macht die **DataView** die **Original** Zeilen Version aller **gelöschten** Zeilen verfügbar, da keine **aktuelle** Zeilen Version vorhanden ist. Mithilfe der **rowversion** -Eigenschaft der **DataRowView**können Sie ermitteln, welche Zeilen Version einer Zeile verfügbar gemacht wird.  
  
     In der folgenden Tabelle sind die Optionen für **DataViewRowState**aufgeführt.  
  
    |"DataViewRowState"-Optionen|Beschreibung|  
    |------------------------------|-----------------|  
    |**CurrentRows**|Die **aktuelle** Zeilen Version aller **unverändert**, **hinzugefügten**und **geänderten** Zeilen. Dies ist die Standardeinstellung.|  
    |**Hinzugefügt**|Die **aktuelle** Zeilen Version aller **hinzugefügten** Zeilen.|  
    |**Lö**|Die **Original** Zeilen Version aller **gelöschten** Zeilen.|  
    |**ModifiedCurrent**|Die **aktuelle** Zeilen Version aller **geänderten** Zeilen.|  
    |**ModifiedOriginal**|Die **Original** Zeilen Version aller **geänderten** Zeilen.|  
    |**Keine**|Keine Zeilen.|  
    |**OriginalRows**|Die **Original** Zeilen Version aller **unverändert**, **geänderten**und **gelöschten** Zeilen.|  
    |**Unverändert**|Die **aktuelle** Zeilen Version aller **unveränderten** Zeilen.|  
  
 Weitere Informationen zu Zeilen Zuständen und Zeilen Versionen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).  
  
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

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataViews](dataviews.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
