---
title: "\"DataTableReaders\""
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785346"
---
# <a name="datatablereaders"></a><span data-ttu-id="fbd04-102">"DataTableReaders"</span><span class="sxs-lookup"><span data-stu-id="fbd04-102">DataTableReaders</span></span>
<span data-ttu-id="fbd04-103">Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.</span><span class="sxs-lookup"><span data-stu-id="fbd04-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="fbd04-104">Wenn Sie einen **DataTableReader** aus einer **Daten**Tabelle erstellen, enthält das resultierende **DataTableReader** -Objekt ein Resultset mit denselben Daten wie die Datentabelle, aus der es erstellt wurde, mit **Ausnahme von Zeilen** , die als Lö.</span><span class="sxs-lookup"><span data-stu-id="fbd04-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="fbd04-105">Die Spalten werden in derselben Reihenfolge wie in der ursprünglichen **Daten**Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbd04-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="fbd04-106">Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch Aufrufen <xref:System.Data.DataSet.CreateDataReader%2A>von erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbd04-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="fbd04-107">Die Ergebnisse sind in derselben Reihenfolge wie die **DataTables** in der Auflistung des **DataSet** - <xref:System.Data.DataSet.Tables%2A> Objekts.</span><span class="sxs-lookup"><span data-stu-id="fbd04-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbd04-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fbd04-108">In This Section</span></span>  
 [<span data-ttu-id="fbd04-109">Erstellen eines DataReader</span><span class="sxs-lookup"><span data-stu-id="fbd04-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="fbd04-110">Erläutert, wie ein **DataTableReader** -Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fbd04-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="fbd04-111">Navigieren in DataTables</span><span class="sxs-lookup"><span data-stu-id="fbd04-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="fbd04-112">Beschreibt die Verwendung der **Read** -Methode, um durch den Inhalt eines **DataTableReader**zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="fbd04-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd04-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd04-113">See also</span></span>

- [<span data-ttu-id="fbd04-114">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fbd04-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="fbd04-115">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fbd04-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
