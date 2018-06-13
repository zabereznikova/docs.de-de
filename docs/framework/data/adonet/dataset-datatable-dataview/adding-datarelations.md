---
title: Hinzufügen von "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 451ee0eee466efca86345ea7112e9b178a2c66e2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756942"
---
# <a name="adding-datarelations"></a><span data-ttu-id="ccac3-102">Hinzufügen von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="ccac3-102">Adding DataRelations</span></span>
<span data-ttu-id="ccac3-103">In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.</span><span class="sxs-lookup"><span data-stu-id="ccac3-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="ccac3-104">Die Argumente erforderlich sind, erstellen eine **DataRelation** sind ein Name für die **DataRelation** erstellt wird, und ein Array aus einem oder mehreren <xref:System.Data.DataColumn> Verweise auf die Spalten, die als die über- und untergeordneten dienen Spalten in der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="ccac3-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="ccac3-105">Nach der Erstellung einer **DataRelation**, können Sie sie zwischen den Tabellen navigieren und Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="ccac3-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="ccac3-106">Hinzufügen einer **DataRelation** auf eine <xref:System.Data.DataSet> hinzufügt, wird standardmäßig ein <xref:System.Data.UniqueConstraint> mit der übergeordneten Tabelle und eine <xref:System.Data.ForeignKeyConstraint> zur untergeordneten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ccac3-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="ccac3-107">Weitere Informationen zu diesen Default-Einschränkungen, finden Sie unter [DataTable-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="ccac3-107">For more information about these default constraints, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="ccac3-108">Das folgende Codebeispiel erstellt eine **DataRelation** unter Verwendung zweier <xref:System.Data.DataTable> Objekte in einem <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ccac3-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ccac3-109">Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen **CustID**, dem dient als Link zwischen den beiden <xref:System.Data.DataTable> Objekte.</span><span class="sxs-lookup"><span data-stu-id="ccac3-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="ccac3-110">Im Beispiel wird eine einzelne **DataRelation** auf die **Beziehungen** Auflistung von der <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ccac3-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ccac3-111">Das erste Argument im Beispiel gibt den Namen des der **DataRelation** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ccac3-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="ccac3-112">Das zweite Argument legt die übergeordnete **DataColumn** und das dritte Argument die untergeordnete **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="ccac3-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="ccac3-113">Ein **DataRelation** verfügt auch über eine **geschachtelte** Eigenschaft, die bei Festlegung auf **"true"**, bewirkt, dass die Zeilen aus der untergeordneten Tabelle in die entsprechenden Zeilen aus der übergeordneten Tabelle geschachtelt werden sollen Wenn als XML-Elemente geschrieben <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="ccac3-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="ccac3-114">Weitere Informationen finden Sie unter [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ccac3-114">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccac3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccac3-115">See Also</span></span>  
 [<span data-ttu-id="ccac3-116">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="ccac3-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ccac3-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ccac3-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
