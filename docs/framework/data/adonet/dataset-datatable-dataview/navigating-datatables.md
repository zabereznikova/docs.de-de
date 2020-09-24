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
# <a name="navigating-datatables"></a><span data-ttu-id="10f49-102">Navigieren in "DataTables"</span><span class="sxs-lookup"><span data-stu-id="10f49-102">Navigating DataTables</span></span>

<span data-ttu-id="10f49-103">Der <xref:System.Data.DataTableReader> ruft den Inhalt eines oder mehrerer <xref:System.Data.DataTable>-Objekte in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets ab.</span><span class="sxs-lookup"><span data-stu-id="10f49-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="10f49-104">Ein <xref:System.Data.DataTableReader> kann mehrere Resultsets enthalten, wenn es mit der <xref:System.Data.DataSet.CreateDataReader%2A>-Methode erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="10f49-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="10f49-105">Die <xref:System.Data.DataTableReader.NextResult%2A>-Methode setzt den Cursor auf das nächste Resultset, wenn mehr als ein Resultset vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="10f49-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="10f49-106">Dabei handelt es sich um einen vorwärts gerichteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="10f49-106">This is a forward-only process.</span></span> <span data-ttu-id="10f49-107">Die Rückkehr zu einem vorhergehenden Resultset ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="10f49-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10f49-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10f49-108">Example</span></span>  

 <span data-ttu-id="10f49-109">Im folgenden Beispiel erstellt die- `TestConstructor` Methode zwei- <xref:System.Data.DataTable> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="10f49-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="10f49-110">Um diesen Konstruktor für die-Klasse zu veranschaulichen <xref:System.Data.DataTableReader> , erstellt das Beispiel einen neuen **DataTableReader** basierend auf einem Array, das die beiden **DataTables**enthält, und führt einen einfachen Vorgang aus, um den Inhalt aus den ersten Spalten in das Konsolenfenster zu drucken.</span><span class="sxs-lookup"><span data-stu-id="10f49-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="10f49-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10f49-111">See also</span></span>

- [<span data-ttu-id="10f49-112">"DataTableReaders"</span><span class="sxs-lookup"><span data-stu-id="10f49-112">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="10f49-113">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10f49-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
