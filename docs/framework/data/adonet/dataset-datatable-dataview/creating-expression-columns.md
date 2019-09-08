---
title: Erstellen von Ausdrucksspalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 1c4e0b368a8eb154207382ae70b9767f5a5fe64d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785436"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="b7b5e-102">Erstellen von Ausdrucksspalten</span><span class="sxs-lookup"><span data-stu-id="b7b5e-102">Creating Expression Columns</span></span>
<span data-ttu-id="b7b5e-103">Sie können einen Ausdruck für eine Spalte definieren, sodass diese einen Wert enthalten kann, der aus anderen Spaltenwerten in der gleichen Zeile oder aus Spaltenwerten mehrerer Zeilen in der Tabelle berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="b7b5e-104">Wenn Sie den auszuwertenden Ausdruck definieren möchten, verwenden Sie die <xref:System.Data.DataColumn.Expression%2A>-Eigenschaft der Zielspalte und verweisen mithilfe der <xref:System.Data.DataColumn.ColumnName%2A>-Eigenschaft auf andere Spalten im Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="b7b5e-105">Der <xref:System.Data.DataColumn.DataType%2A> für die Ausdrucksspalte muss für den Wert geeignet sein, den der Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="b7b5e-106">In der folgenden Tabelle werden Verwendungsmöglichkeiten für Ausdrucksspalten in einer Tabelle aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="b7b5e-107">Ausdruckstyp</span><span class="sxs-lookup"><span data-stu-id="b7b5e-107">Expression type</span></span>|<span data-ttu-id="b7b5e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7b5e-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="b7b5e-109">Vergleich</span><span class="sxs-lookup"><span data-stu-id="b7b5e-109">Comparison</span></span>|<span data-ttu-id="b7b5e-110">"Gesamt > = 500"</span><span class="sxs-lookup"><span data-stu-id="b7b5e-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="b7b5e-111">Berechnung</span><span class="sxs-lookup"><span data-stu-id="b7b5e-111">Computation</span></span>|<span data-ttu-id="b7b5e-112">"Einzelpreis \* Menge"</span><span class="sxs-lookup"><span data-stu-id="b7b5e-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="b7b5e-113">Aggregation</span><span class="sxs-lookup"><span data-stu-id="b7b5e-113">Aggregation</span></span>|<span data-ttu-id="b7b5e-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="b7b5e-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="b7b5e-115">Sie können die **Expression** -Eigenschaft für ein vorhandenes **datacolenumn** -Objekt festlegen, oder Sie können die-Eigenschaft als drittes Argument, <xref:System.Data.DataColumn> das an den-Konstruktor übergeben wird, einschließen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="b7b5e-116">Ausdrücke können auf andere Ausdrucksspalten verweisen. Ein Zirkelverweis, bei dem zwei Ausdrücke aufeinander verweisen, generiert jedoch eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="b7b5e-117">Regeln zum Schreiben von Ausdrücken finden Sie unter <xref:System.Data.DataColumn.Expression%2A> der-Eigenschaft der **datacolenumn** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="b7b5e-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b5e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7b5e-118">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="b7b5e-119">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="b7b5e-119">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="b7b5e-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="b7b5e-120">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="b7b5e-121">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b7b5e-121">ADO.NET Overview</span></span>](../ado-net-overview.md)
