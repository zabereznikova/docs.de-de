---
title: "Erstellen eines &#39;DataReader&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Erstellen eines &#39;DataReader&#39;
Die <xref:System.Data.DataTable>\-Klasse und die <xref:System.Data.DataSet>\-Klasse verfügen über eine <xref:System.Data.DataTable.CreateDataReader%2A>\-Methode, die den Inhalt der <xref:System.Data.DataTable> oder den Inhalt der <xref:System.Data.DataSet.Tables%2A>\-Auflistung des <xref:System.Data.DataSet>\-Objekts als ein oder mehrere schreibgeschützte vorwärtsgerichtete Resultsets zurückgibt.  
  
## Beispiel  
 Die folgende Konsolenanwendung erstellt eine <xref:System.Data.DataTable>\-Instanz.  Im Beispiel wird anschließend die gefüllte <xref:System.Data.DataTable> ``  an eine Prozedur übergeben, die die <xref:System.Data.DataTable.CreateDataReader%2A>\-Methode aufruft. Diese durchläuft die im <xref:System.Data.DataTableReader> enthaltenen Ergebnisse.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 Im Beispiel wird die folgende Ausgabe im Konsolenfenster angezeigt:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## Siehe auch  
 <xref:System.Data.DataTable.CreateDataReader%2A>   
 <xref:System.Data.DataSet.CreateDataReader%2A>   
 ['DataTableReaders'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)