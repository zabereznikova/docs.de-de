---
title: Erstellen eines "DataReader"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: c5073a553926fdfdd78b0b6837cdc07b58ac7faf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755512"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="63556-102">Erstellen eines "DataReader"</span><span class="sxs-lookup"><span data-stu-id="63556-102">Creating a DataReader</span></span>
<span data-ttu-id="63556-103">Die <xref:System.Data.DataTable>-Klasse und die <xref:System.Data.DataSet>-Klasse verfügen über eine <xref:System.Data.DataTable.CreateDataReader%2A>-Methode, die den Inhalt der <xref:System.Data.DataTable> oder den Inhalt der <xref:System.Data.DataSet>-Auflistung des <xref:System.Data.DataSet.Tables%2A>-Objekts als ein oder mehrere schreibgeschützte vorwärtsgerichtete Resultsets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63556-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63556-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63556-104">Example</span></span>  
 <span data-ttu-id="63556-105">Die folgende Konsolenanwendung erstellt eine <xref:System.Data.DataTable>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="63556-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="63556-106">Im Beispiel übergibt dann das ausgefüllte <xref:System.Data.DataTable> an eine Prozedur, die Aufrufe der <xref:System.Data.DataTable.CreateDataReader%2A> -Methode, die Ergebnisse der enthaltenen durchläuft die <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="63556-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="63556-107">Im Beispiel wird die folgende Ausgabe im Konsolenfenster angezeigt:</span><span class="sxs-lookup"><span data-stu-id="63556-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="63556-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63556-108">See Also</span></span>  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [<span data-ttu-id="63556-109">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="63556-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="63556-110">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="63556-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
