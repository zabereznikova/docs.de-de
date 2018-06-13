---
title: Erstellen eines "DataSets"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: 3c48b430b1a087a79db37398b2c68014b8077c55
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755964"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="a248d-102">Erstellen eines "DataSets"</span><span class="sxs-lookup"><span data-stu-id="a248d-102">Creating a DataSet</span></span>
<span data-ttu-id="a248d-103">Durch Aufrufen des <xref:System.Data.DataSet>-Konstruktors wird eine Instanz eines <xref:System.Data.DataSet> erstellt.</span><span class="sxs-lookup"><span data-stu-id="a248d-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="a248d-104">Optional kann ein Argument für den Namen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a248d-104">Optionally specify a name argument.</span></span> <span data-ttu-id="a248d-105">Wenn für das <xref:System.Data.DataSet> kein Name angegeben wird, wird der Name auf "NewDataSet" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a248d-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="a248d-106">Sie können auch ein neues <xref:System.Data.DataSet> auf der Grundlage eines vorhandenen <xref:System.Data.DataSet> erstellen.</span><span class="sxs-lookup"><span data-stu-id="a248d-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a248d-107">Das neue <xref:System.Data.DataSet> kann eine exakte Kopie des vorhandenen <xref:System.Data.DataSet> sein. Es kann ein Klon des <xref:System.Data.DataSet> sein, der die relationale Struktur oder das relationale Schema kopiert, aber keine Daten aus dem vorhandenen <xref:System.Data.DataSet> enthält. Es kann auch eine mithilfe der <xref:System.Data.DataSet>-Methode erstellte Teilmenge des <xref:System.Data.DataSet> sein, das nur die geänderten Zeilen aus dem vorhandenen <xref:System.Data.DataSet.GetChanges%2A> enthält.</span><span class="sxs-lookup"><span data-stu-id="a248d-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="a248d-108">Weitere Informationen finden Sie unter [Kopieren von DataSet-Inhalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span><span class="sxs-lookup"><span data-stu-id="a248d-108">For more information, see [Copying DataSet Contents](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="a248d-109">Im folgenden Codebeispiel wird das Erstellen einer Instanz eines <xref:System.Data.DataSet> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a248d-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="a248d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a248d-110">See Also</span></span>  
 [<span data-ttu-id="a248d-111">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="a248d-111">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="a248d-112">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="a248d-112">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="a248d-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a248d-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
