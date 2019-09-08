---
title: Hinzufügen von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 8157d296636d0f8661a35af35de561f5cc49c30b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784812"
---
# <a name="adding-datarelations"></a><span data-ttu-id="1d2a9-102">Hinzufügen von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="1d2a9-102">Adding DataRelations</span></span>
<span data-ttu-id="1d2a9-103">In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="1d2a9-104">Die Argumente, die zum Erstellen einer **DataRelations** erforderlich sind, sind ein Name für die zu **erstellende DataRelations** und ein <xref:System.Data.DataColumn> Array mit einem oder mehreren verweisen auf die Spalten, die als übergeordnete und untergeordnete Spalten in der Beziehung fungieren.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="1d2a9-105">Nachdem Sie eine **DataRelations**erstellt haben, können Sie Sie zum Navigieren zwischen den Tabellen und zum Abrufen von Werten verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="1d2a9-106">Beim Hinzufügen einer **DataRelations** zu einer <xref:System.Data.DataSet> wird der übergeordneten <xref:System.Data.UniqueConstraint> Tabelle <xref:System.Data.ForeignKeyConstraint> standardmäßig ein hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="1d2a9-107">Weitere Informationen zu diesen Standard Einschränkungen finden Sie unter [databel-Einschränkungen](datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="1d2a9-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="1d2a9-108">Im folgenden Codebeispiel wird eine **DataRelations** mithilfe von <xref:System.Data.DataTable> zwei-Objekten <xref:System.Data.DataSet>in einem erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1d2a9-109">Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen " **CustId**", die als Link zwischen <xref:System.Data.DataTable> den beiden Objekten dient.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="1d2a9-110">Im Beispiel wird der **Beziehungs** Auflistung von <xref:System.Data.DataSet>eine einzelne **DataRelations** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1d2a9-111">Das erste Argument im Beispiel gibt den Namen der zu **erstellenden DataRelations** an.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="1d2a9-112">Mit dem zweiten Argument wird die übergeordnete **datacolumschlag** festgelegt, und das dritte Argument legt die untergeordnete **datacolumschlag**fest.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="1d2a9-113">Eine **DataRelations** verfügt auch über eine geschachtelte **Eigenschaft,** die bei Festlegung auf **true**bewirkt, dass die Zeilen aus der untergeordneten Tabelle in der zugeordneten Zeile aus der übergeordneten Tabelle geschachtelt <xref:System.Data.DataSet.WriteXml%2A> werden, wenn Sie mithilfe von als XML-Elemente geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1d2a9-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="1d2a9-114">Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="1d2a9-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2a9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d2a9-115">See also</span></span>

- [<span data-ttu-id="1d2a9-116">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="1d2a9-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="1d2a9-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1d2a9-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
