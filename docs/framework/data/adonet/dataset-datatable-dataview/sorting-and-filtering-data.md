---
title: "Sortieren und Filtern von Daten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Sortieren und Filtern von Daten
Die <xref:System.Data.DataView> stellt mehrere Methoden zum Sortieren und Filtern von Daten in einer <xref:System.Data.DataTable> bereit:  
  
-   Mit der <xref:System.Data.DataView.Sort%2A>\-Eigenschaft können Sie einzelne oder mehrere Sortierreihenfolgen für Spalten angeben und die Parameter ASC \(ascending \= aufsteigend\) und DESC \(descending \= absteigend\) einfügen.  
  
-   Sie können mithilfe der <xref:System.Data.DataView.ApplyDefaultSort%2A>\-Eigenschaft automatisch eine Sortierreihenfolge in aufsteigender Reihenfolge auf Grundlage der Primärschlüsselspalte bzw. \-spalten der Tabelle erstellen.  <xref:System.Data.DataView.ApplyDefaultSort%2A> ist nur gültig, wenn die **Sort**\-Eigenschaft ein NULL\-Verweis oder eine leere Zeichenfolge ist für die Tabelle ein Primärschlüssel definiert ist.  
  
-   Mit der <xref:System.Data.DataView.RowFilter%2A>\-Eigenschaft können Sie Teilmengen von Zeilen angeben, die auf den Spaltenwerten basieren.  Ausführliche Informationen zu gültigen Ausdrücken für die **RowFilter**\-Eigenschaft finden Sie in den Referenzinformationen für die <xref:System.Data.DataColumn.Expression%2A>\-Eigenschaft der <xref:System.Data.DataColumn>\-Klasse.  
  
     Wenn Sie die Ergebnisse einer bestimmten Abfrage von Daten zurückgeben möchten, anstatt eine dynamische Ansicht von einer Teilmenge von Daten zu erhalten, verwenden Sie die <xref:System.Data.DataView.Find%2A>\-Methode oder die <xref:System.Data.DataView.FindRows%2A>\-Methode der **DataView**, denn sie sind für diesen Zweck besser geeignet als die **RowFilter**\-Eigenschaft.  Wenn Sie die **RowFilter**\-Eigenschaft festlegen, wird der Index für die Daten neu erstellt, wodurch zusätzlicher Verwaltungsmehraufwand für die Anwendung entsteht und die Leistung verringert wird.  Die **RowFilter**\-Eigenschaft wird am besten in einer datengebundenen Anwendung verwendet, in der ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt.  Die Methoden **Find** und **FindRows** nutzen den aktuellen Index, ohne dass der Index neu erstellt werden muss.  Weitere Informationen zu den Methoden **Find** und **FindRows** finden Sie unter [Suchen nach Zeilen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   Mit der <xref:System.Data.DataView.RowStateFilter%2A>\-Eigenschaft können Sie festlegen, welche Zeilenversionen Sie anzeigen möchten.  Die **DataView** verwaltet implizit, welche Zeilenversion, abhängig vom **RowState** der zugrunde liegenden Zeile, verfügbar gemacht werden soll.  Wenn z. B. der **RowStateFilter** auf **DataViewRowState.Deleted** festgelegt ist, macht die **DataView** die **Original**\-Zeilenversion aller **Deleted**\-Zeilen verfügbar, da keine **Current**\-Zeilenversion vorliegt.  Mit der **RowVersion**\-Eigenschaft der **DataRowView** können Sie bestimmen, welche Zeilenversion einer Zeile verfügbar gemacht wird.  
  
     In der folgenden Tabelle sind die Optionen für **DataViewRowState** enthalten.  
  
    |"DataViewRowState"\-Optionen|Beschreibung|  
    |----------------------------------|------------------|  
    |**CurrentRows**|Die **Current**\-Zeilenversion von allen Zeilen mit dem Status **Unchanged**, **Added** und **Modified**.  Dies ist die Standardeinstellung.|  
    |**Added**|Die **Current**\-Zeilenversion von allen **Added**\-Zeilen.|  
    |**Deleted**|Die **Original**\-Zeilenversion von allen **Deleted**\-Zeilen.|  
    |**ModifiedCurrent**|Die **Current**\-Zeilenversion von allen **Modified**\-Zeilen.|  
    |**ModifiedOriginal**|Die **Original**\-Zeilenversion von allen **Modified**\-Zeilen.|  
    |**Keine**|Keine Zeilen.|  
    |**OriginalRows**|Die **Original**\-Zeilenversion von allen Zeilen mit dem Status **Unchanged**, **Modified** und **Deleted**.|  
    |**Unchanged**|Die **Current**\-Zeilenversion von allen **Unchanged**\-Zeilen.|  
  
 Weitere Informationen zu Zeilenzuständen und Zeilenversionen finden Sie unter [Zeilenstatus und Zeilenversion](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 Im folgenden Codebeispiel wird eine Ansicht erstellt, die alle Produkte anzeigt, bei denen die Anzahl der Einheiten im Lager kleiner als oder gleich der Neusortierungsebene ist, wobei zuerst nach der Lieferanten\-ID und dann nach dem Produktnamen sortiert wird.  
  
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
  
## Siehe auch  
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)