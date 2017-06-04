---
title: "Navigieren in &#39;DataTables&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Navigieren in &#39;DataTables&#39;
Der <xref:System.Data.DataTableReader> ruft den Inhalt eines oder mehrerer <xref:System.Data.DataTable>\-Objekte in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets ab.  
  
 Ein <xref:System.Data.DataTableReader> kann mehrere Resultsets enthalten, wenn es mit der <xref:System.Data.DataSet.CreateDataReader%2A>\-Methode erstellt wird.  Die <xref:System.Data.DataTableReader.NextResult%2A>\-Methode setzt den Cursor auf das nächste Resultset, wenn mehr als ein Resultset vorhanden ist.  Dabei handelt es sich um einen vorwärts gerichteten Prozess.  Die Rückkehr zu einem vorhergehenden Resultset ist nicht möglich.  
  
## Beispiel  
 Im folgenden Beispiel werden mit der `TestConstructor`\-Methode zwei <xref:System.Data.DataTable> `` \-Instanzen erstellt.  In diesem Beispiel wird ein neuer **DataTableReader** auf der Grundlage eines Arrays erstellt, das die beiden **DataTables** enthält, und ein einfacher Vorgang wird ausgeführt, bei dem der Inhalt der ersten Spalten im Konsolenfenster ausgegeben wird, um diesen Konstruktor für die <xref:System.Data.DataTableReader>\-Klasse zu veranschaulichen.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## Siehe auch  
 ['DataTableReaders'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)