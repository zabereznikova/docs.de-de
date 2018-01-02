---
title: "\"DataTableReaders\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0e3f3da6554239b4f04e244d3339a4280e1add85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datatablereaders"></a><span data-ttu-id="e3b46-102">"DataTableReaders"</span><span class="sxs-lookup"><span data-stu-id="e3b46-102">DataTableReaders</span></span>
<span data-ttu-id="e3b46-103">Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.</span><span class="sxs-lookup"><span data-stu-id="e3b46-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="e3b46-104">Beim Erstellen einer **DataTableReader** aus einem **DataTable**, das resultierende **DataTableReader** Objekt enthält die gleichen Daten wie ein Resultset der  **DataTable** aus dem er, mit Ausnahme von Zeilen erstellt wurde, die als gelöscht markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e3b46-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="e3b46-105">Die Spalten angezeigt werden, in der gleichen Reihenfolge wie in der ursprünglichen **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="e3b46-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="e3b46-106">Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch den Aufruf erstellt wurde <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3b46-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="e3b46-107">Die Ergebnisse werden in der gleichen Reihenfolge wie die **DataTables** in der **DataSet** des Objekts <xref:System.Data.DataSet.Tables%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e3b46-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3b46-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e3b46-108">In This Section</span></span>  
 [<span data-ttu-id="e3b46-109">Erstellen eines DataReader</span><span class="sxs-lookup"><span data-stu-id="e3b46-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="e3b46-110">Erläutert das Erstellen einer **DataTableReader** Objekt.</span><span class="sxs-lookup"><span data-stu-id="e3b46-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="e3b46-111">Navigieren in DataTables</span><span class="sxs-lookup"><span data-stu-id="e3b46-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="e3b46-112">Beschreibt die Verwendung von der **lesen** -Methode durch den Inhalt des Verschieben einer **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="e3b46-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b46-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3b46-113">See Also</span></span>  
 [<span data-ttu-id="e3b46-114">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e3b46-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="e3b46-115">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e3b46-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
