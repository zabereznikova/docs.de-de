---
title: Erstellen eines "DataReader"
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
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 05b3943613a6ab03e77dee7fb8262029618b5c7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-datareader"></a>Erstellen eines "DataReader"
Die <xref:System.Data.DataTable>-Klasse und die <xref:System.Data.DataSet>-Klasse verfügen über eine <xref:System.Data.DataTable.CreateDataReader%2A>-Methode, die den Inhalt der <xref:System.Data.DataTable> oder den Inhalt der <xref:System.Data.DataSet>-Auflistung des <xref:System.Data.DataSet.Tables%2A>-Objekts als ein oder mehrere schreibgeschützte vorwärtsgerichtete Resultsets zurückgibt.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung erstellt eine <xref:System.Data.DataTable>-Instanz. Im Beispiel übergibt dann das ausgefüllte <xref:System.Data.DataTable> an eine Prozedur, die Aufrufe der <xref:System.Data.DataTable.CreateDataReader%2A> -Methode, die Ergebnisse der enthaltenen durchläuft die <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 Im Beispiel wird die folgende Ausgabe im Konsolenfenster angezeigt:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
