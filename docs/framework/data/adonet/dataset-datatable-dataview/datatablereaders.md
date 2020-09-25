---
title: "\"DataTableReaders\""
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202317"
---
# <a name="datatablereaders"></a><span data-ttu-id="9224d-102">"DataTableReaders"</span><span class="sxs-lookup"><span data-stu-id="9224d-102">DataTableReaders</span></span>

<span data-ttu-id="9224d-103">Der <xref:System.Data.DataTableReader> stellt den Inhalt einer <xref:System.Data.DataTable> oder eines <xref:System.Data.DataSet> in Form eines oder mehrerer schreibgeschützter vorwärts gerichteter Resultsets dar.</span><span class="sxs-lookup"><span data-stu-id="9224d-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="9224d-104">Wenn Sie einen **DataTableReader** aus einer **Daten**Tabelle erstellen, enthält das resultierende **DataTableReader** -Objekt ein Resultset mit denselben Daten wie die Datentabelle, aus der es erstellt wurde, mit **Ausnahme von Zeilen** , die als gelöscht markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9224d-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="9224d-105">Die Spalten werden in derselben Reihenfolge wie in der ursprünglichen **Daten**Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9224d-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="9224d-106">Ein **DataTableReader** kann mehrere Resultsets enthalten, wenn er durch Aufrufen von erstellt wurde <xref:System.Data.DataSet.CreateDataReader%2A> .</span><span class="sxs-lookup"><span data-stu-id="9224d-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="9224d-107">Die Ergebnisse sind in derselben Reihenfolge wie die **DataTables** in der Auflistung des **DataSet** -Objekts <xref:System.Data.DataSet.Tables%2A> .</span><span class="sxs-lookup"><span data-stu-id="9224d-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9224d-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9224d-108">In This Section</span></span>  

 [<span data-ttu-id="9224d-109">Erstellen eines "DataReader"</span><span class="sxs-lookup"><span data-stu-id="9224d-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="9224d-110">Erläutert, wie ein **DataTableReader** -Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9224d-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="9224d-111">Navigieren in "DataTables"</span><span class="sxs-lookup"><span data-stu-id="9224d-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="9224d-112">Beschreibt die Verwendung der **Read** -Methode, um durch den Inhalt eines **DataTableReader**zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="9224d-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9224d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9224d-113">See also</span></span>

- [<span data-ttu-id="9224d-114">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9224d-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="9224d-115">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9224d-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
