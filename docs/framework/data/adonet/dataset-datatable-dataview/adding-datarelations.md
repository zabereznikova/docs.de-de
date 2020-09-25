---
title: Hinzufügen von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202382"
---
# <a name="adding-datarelations"></a><span data-ttu-id="bd08a-102">Hinzufügen von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="bd08a-102">Adding DataRelations</span></span>

<span data-ttu-id="bd08a-103">In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.</span><span class="sxs-lookup"><span data-stu-id="bd08a-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="bd08a-104">Die Argumente, die zum Erstellen einer **DataRelations** erforderlich sind, sind ein Name für die zu **erstellende DataRelations** und ein Array mit einem oder mehreren <xref:System.Data.DataColumn> verweisen auf die Spalten, die als übergeordnete und untergeordnete Spalten in der Beziehung fungieren.</span><span class="sxs-lookup"><span data-stu-id="bd08a-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="bd08a-105">Nachdem Sie eine **DataRelations**erstellt haben, können Sie Sie zum Navigieren zwischen den Tabellen und zum Abrufen von Werten verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd08a-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="bd08a-106">Beim Hinzufügen einer **DataRelations** zu einer wird der über <xref:System.Data.DataSet> geordneten Tabelle standardmäßig ein hinzugefügt <xref:System.Data.UniqueConstraint> <xref:System.Data.ForeignKeyConstraint> .</span><span class="sxs-lookup"><span data-stu-id="bd08a-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="bd08a-107">Weitere Informationen zu diesen Standard Einschränkungen finden Sie unter [databel-Einschränkungen](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="bd08a-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="bd08a-108">Im folgenden Codebeispiel wird eine **DataRelations** mithilfe von zwei- <xref:System.Data.DataTable> Objekten in einem erstellt <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="bd08a-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bd08a-109">Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen " **CustId**", die als Link zwischen den beiden <xref:System.Data.DataTable> Objekten dient.</span><span class="sxs-lookup"><span data-stu-id="bd08a-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="bd08a-110">Im Beispiel wird der **Beziehungs** Auflistung von eine einzelne **DataRelations** hinzugefügt <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="bd08a-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bd08a-111">Das erste Argument im Beispiel gibt den Namen der zu **erstellenden DataRelations** an.</span><span class="sxs-lookup"><span data-stu-id="bd08a-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="bd08a-112">Mit dem zweiten Argument wird die übergeordnete **datacolumschlag** festgelegt, und das dritte Argument legt die untergeordnete **datacolumschlag**fest.</span><span class="sxs-lookup"><span data-stu-id="bd08a-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="bd08a-113">Eine **DataRelations** verfügt auch über eine geschachtelte **Eigenschaft,** die bei Festlegung auf **true**bewirkt, dass die Zeilen aus der untergeordneten Tabelle in der zugeordneten Zeile aus der übergeordneten Tabelle geschachtelt werden, wenn Sie mithilfe von als XML-Elemente geschrieben werden <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="bd08a-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="bd08a-114">Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="bd08a-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd08a-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd08a-115">See also</span></span>

- [<span data-ttu-id="bd08a-116">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="bd08a-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bd08a-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bd08a-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
