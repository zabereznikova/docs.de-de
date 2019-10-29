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
# <a name="creating-a-datareader"></a><span data-ttu-id="e35ba-102">Erstellen eines "DataReader"</span><span class="sxs-lookup"><span data-stu-id="e35ba-102">Creating a DataReader</span></span>
<span data-ttu-id="e35ba-103">Die <xref:System.Data.DataTable>-Klasse und die <xref:System.Data.DataSet>-Klasse verfügen über eine <xref:System.Data.DataTable.CreateDataReader%2A>-Methode, die den Inhalt der <xref:System.Data.DataTable> oder den Inhalt der <xref:System.Data.DataSet>-Auflistung des <xref:System.Data.DataSet.Tables%2A>-Objekts als ein oder mehrere schreibgeschützte vorwärtsgerichtete Resultsets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e35ba-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e35ba-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e35ba-104">Example</span></span>  
 <span data-ttu-id="e35ba-105">Die folgende Konsolenanwendung erstellt eine <xref:System.Data.DataTable>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e35ba-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="e35ba-106">Im Beispiel wird dann das gefüllte <xref:System.Data.DataTable> an eine Prozedur weitergeleitet, die die <xref:System.Data.DataTable.CreateDataReader%2A>-Methode aufruft, die die im <xref:System.Data.DataTableReader>enthaltenen Ergebnisse durchläuft.</span><span class="sxs-lookup"><span data-stu-id="e35ba-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="e35ba-107">Im Beispiel wird die folgende Ausgabe im Konsolenfenster angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e35ba-107">The example displays the following output in the console window:</span></span>  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="e35ba-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e35ba-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="e35ba-109">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="e35ba-109">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="e35ba-110">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e35ba-110">ADO.NET Overview</span></span>](../ado-net-overview.md)
