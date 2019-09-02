---
title: Navigieren in "DataTables"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: b5837d647b72f8dd17c4a6d3664faf8976243d36
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204557"
---
# <a name="navigating-datatables"></a>Navigieren in "DataTables"
Der <xref:System.Data.DataTableReader> ruft den Inhalt eines oder mehrerer <xref:System.Data.DataTable>-Objekte in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets ab.  
  
 Ein <xref:System.Data.DataTableReader> kann mehrere Resultsets enthalten, wenn es mit der <xref:System.Data.DataSet.CreateDataReader%2A>-Methode erstellt wird. Die <xref:System.Data.DataTableReader.NextResult%2A>-Methode setzt den Cursor auf das nächste Resultset, wenn mehr als ein Resultset vorhanden ist. Dabei handelt es sich um einen vorwärts gerichteten Prozess. Die Rückkehr zu einem vorhergehenden Resultset ist nicht möglich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel erstellt die `TestConstructor` -Methode zwei <xref:System.Data.DataTable> -Instanzen. Um diesen Konstruktor für die <xref:System.Data.DataTableReader> -Klasse zu veranschaulichen, erstellt das Beispiel einen neuen **DataTableReader** basierend auf einem Array, das die beiden **DataTables**enthält, und führt einen einfachen Vorgang aus. dabei wird der Inhalt aus den ersten Spalten im Konsolenfenster.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [DataTableReaders](datatablereaders.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
