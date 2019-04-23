---
title: Navigieren in "DataTables"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 91db42acb0e09b8fc99b0ee710a60800d40938ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112852"
---
# <a name="navigating-datatables"></a>Navigieren in "DataTables"
Der <xref:System.Data.DataTableReader> ruft den Inhalt eines oder mehrerer <xref:System.Data.DataTable>-Objekte in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets ab.  
  
 Ein <xref:System.Data.DataTableReader> kann mehrere Resultsets enthalten, wenn es mit der <xref:System.Data.DataSet.CreateDataReader%2A>-Methode erstellt wird. Die <xref:System.Data.DataTableReader.NextResult%2A>-Methode setzt den Cursor auf das nächste Resultset, wenn mehr als ein Resultset vorhanden ist. Dabei handelt es sich um einen vorwärts gerichteten Prozess. Die Rückkehr zu einem vorhergehenden Resultset ist nicht möglich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel die `TestConstructor` Methode erstellt zwei <xref:System.Data.DataTable> Instanzen. Um diesen Konstruktor für veranschaulichen die <xref:System.Data.DataTableReader> -Klasse, die das Beispiel erstellt ein neues **DataTableReader** basierend auf ein Array mit den beiden **DataTables**, und führt einen einfachen Vorgang Drucken Sie den Inhalt in der ersten Spalten an, an das Konsolenfenster.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
