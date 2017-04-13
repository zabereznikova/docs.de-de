---
title: "&#39;DataTableReaders&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# &#39;DataTableReaders&#39;
Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.  
  
 Wenn ein **DataTableReader** aus einer **DataTable** erstellt wird, enthält das entstehende **DataTableReader**\-Objekt ein Resultset, das dieselben Daten wie die **DataTable** enthält, aus der es erstellt wurde. Eine Ausnahme bilden die Zeilen, die als gelöscht markiert wurden.  Die Spalten werden in derselben Reihenfolge wie in der ursprünglichen **DataTable** angezeigt.  
  
 Ein **DataTableReader** kann mehre Resultsets enthalten, wenn er durch einen Aufruf von <xref:System.Data.DataSet.CreateDataReader%2A> erstellt wurde.  Die Ergebnisse werden in derselben Reihenfolge wie die **DataTables** in der <xref:System.Data.DataSet.Tables%2A>\-Auflistung des **DataSet**\-Objekts zurückgegeben.  
  
## In diesem Abschnitt  
 [Erstellen eines 'DataReader'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Erläutert das Erstellen eines **DataTableReader**\-Objekts.  
  
 [Navigieren in 'DataTables'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Beschreibt die Verwendung der **Read**\-Methode zum Durchlaufen des Inhalts eines **DataTableReader**.  
  
## Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)