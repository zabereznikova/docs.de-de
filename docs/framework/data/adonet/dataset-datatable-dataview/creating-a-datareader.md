---
title: Erstellen eines "DataReader"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 696eb4dfc334390e1968dd317d441f3c987a1f77
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040114"
---
# <a name="creating-a-datareader"></a>Erstellen eines "DataReader"
Die <xref:System.Data.DataTable>-Klasse und die <xref:System.Data.DataSet>-Klasse verfügen über eine <xref:System.Data.DataTable.CreateDataReader%2A>-Methode, die den Inhalt der <xref:System.Data.DataTable> oder den Inhalt der <xref:System.Data.DataSet>-Auflistung des <xref:System.Data.DataSet.Tables%2A>-Objekts als ein oder mehrere schreibgeschützte vorwärtsgerichtete Resultsets zurückgibt.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung erstellt eine <xref:System.Data.DataTable>-Instanz. Im Beispiel wird dann das gefüllte <xref:System.Data.DataTable> an eine Prozedur weitergeleitet, die die <xref:System.Data.DataTable.CreateDataReader%2A>-Methode aufruft, die die im <xref:System.Data.DataTableReader>enthaltenen Ergebnisse durchläuft.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 Im Beispiel wird die folgende Ausgabe im Konsolenfenster angezeigt:  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [DataTableReaders](datatablereaders.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
