---
title: Navigieren in "DataTables"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148307"
---
# <a name="navigating-datatables"></a>Navigieren in "DataTables"

Der <xref:System.Data.DataTableReader> ruft den Inhalt eines oder mehrerer <xref:System.Data.DataTable>-Objekte in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets ab.  
  
 Ein <xref:System.Data.DataTableReader> kann mehrere Resultsets enthalten, wenn es mit der <xref:System.Data.DataSet.CreateDataReader%2A>-Methode erstellt wird. Die <xref:System.Data.DataTableReader.NextResult%2A>-Methode setzt den Cursor auf das nächste Resultset, wenn mehr als ein Resultset vorhanden ist. Dabei handelt es sich um einen vorwärts gerichteten Prozess. Die Rückkehr zu einem vorhergehenden Resultset ist nicht möglich.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel erstellt die- `TestConstructor` Methode zwei- <xref:System.Data.DataTable> Instanzen. Um diesen Konstruktor für die-Klasse zu veranschaulichen <xref:System.Data.DataTableReader> , erstellt das Beispiel einen neuen **DataTableReader** basierend auf einem Array, das die beiden **DataTables**enthält, und führt einen einfachen Vorgang aus, um den Inhalt aus den ersten Spalten in das Konsolenfenster zu drucken.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- ["DataTableReaders"](datatablereaders.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
