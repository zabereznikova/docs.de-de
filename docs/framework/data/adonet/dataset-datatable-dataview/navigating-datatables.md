---
title: Navigieren in "DataTables"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: f00e2171c1adf4ff99a669085131ebc8d38f7006
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837546"
---
# <a name="navigating-datatables"></a><span data-ttu-id="1e6cd-102">Navigieren in "DataTables"</span><span class="sxs-lookup"><span data-stu-id="1e6cd-102">Navigating DataTables</span></span>
<span data-ttu-id="1e6cd-103">Der <xref:System.Data.DataTableReader> ruft den Inhalt eines oder mehrerer <xref:System.Data.DataTable>-Objekte in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets ab.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="1e6cd-104">Ein <xref:System.Data.DataTableReader> kann mehrere Resultsets enthalten, wenn es mit der <xref:System.Data.DataSet.CreateDataReader%2A>-Methode erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="1e6cd-105">Die <xref:System.Data.DataTableReader.NextResult%2A>-Methode setzt den Cursor auf das nächste Resultset, wenn mehr als ein Resultset vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="1e6cd-106">Dabei handelt es sich um einen vorwärts gerichteten Prozess.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-106">This is a forward-only process.</span></span> <span data-ttu-id="1e6cd-107">Die Rückkehr zu einem vorhergehenden Resultset ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e6cd-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e6cd-108">Example</span></span>  
 <span data-ttu-id="1e6cd-109">Im folgenden Beispiel die `TestConstructor` Methode erstellt zwei <xref:System.Data.DataTable> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="1e6cd-110">Um diesen Konstruktor für veranschaulichen die <xref:System.Data.DataTableReader> -Klasse, die das Beispiel erstellt ein neues **DataTableReader** basierend auf ein Array mit den beiden **DataTables**, und führt einen einfachen Vorgang Drucken Sie den Inhalt in der ersten Spalten an, an das Konsolenfenster.</span><span class="sxs-lookup"><span data-stu-id="1e6cd-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1e6cd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e6cd-111">See Also</span></span>  
 [<span data-ttu-id="1e6cd-112">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="1e6cd-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="1e6cd-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1e6cd-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
