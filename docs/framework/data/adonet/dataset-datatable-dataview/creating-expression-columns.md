---
title: Erstellen von Ausdrucksspalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: db38d42e9c7dc1657e06030599ae2b8ba66ef6b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549875"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="5ed4e-102">Erstellen von Ausdrucksspalten</span><span class="sxs-lookup"><span data-stu-id="5ed4e-102">Creating Expression Columns</span></span>
<span data-ttu-id="5ed4e-103">Sie können einen Ausdruck für eine Spalte definieren, sodass diese einen Wert enthalten kann, der aus anderen Spaltenwerten in der gleichen Zeile oder aus Spaltenwerten mehrerer Zeilen in der Tabelle berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="5ed4e-104">Wenn Sie den auszuwertenden Ausdruck definieren möchten, verwenden Sie die <xref:System.Data.DataColumn.Expression%2A>-Eigenschaft der Zielspalte und verweisen mithilfe der <xref:System.Data.DataColumn.ColumnName%2A>-Eigenschaft auf andere Spalten im Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="5ed4e-105">Der <xref:System.Data.DataColumn.DataType%2A> für die Ausdrucksspalte muss für den Wert geeignet sein, den der Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="5ed4e-106">In der folgenden Tabelle werden Verwendungsmöglichkeiten für Ausdrucksspalten in einer Tabelle aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="5ed4e-107">Ausdruckstyp</span><span class="sxs-lookup"><span data-stu-id="5ed4e-107">Expression type</span></span>|<span data-ttu-id="5ed4e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ed4e-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="5ed4e-109">Vergleich</span><span class="sxs-lookup"><span data-stu-id="5ed4e-109">Comparison</span></span>|<span data-ttu-id="5ed4e-110">"Gesamtsumme >= 500"</span><span class="sxs-lookup"><span data-stu-id="5ed4e-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="5ed4e-111">Berechnung</span><span class="sxs-lookup"><span data-stu-id="5ed4e-111">Computation</span></span>|<span data-ttu-id="5ed4e-112">"Einzelpreis \* Menge"</span><span class="sxs-lookup"><span data-stu-id="5ed4e-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="5ed4e-113">Aggregation</span><span class="sxs-lookup"><span data-stu-id="5ed4e-113">Aggregation</span></span>|<span data-ttu-id="5ed4e-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="5ed4e-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="5ed4e-115">Sie können festlegen, die **Ausdruck** -Eigenschaft für ein vorhandenes **DataColumn** -Objekt, oder Sie können nehmen Sie die Eigenschaft als dritte Argument übergeben die <xref:System.Data.DataColumn> -Konstruktor, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="5ed4e-116">Ausdrücke können auf andere Ausdrucksspalten verweisen. Ein Zirkelverweis, bei dem zwei Ausdrücke aufeinander verweisen, generiert jedoch eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="5ed4e-117">Regeln zum Schreiben von Ausdrücken finden Sie unter den <xref:System.Data.DataColumn.Expression%2A> Eigenschaft der **DataColumn** Klasse.</span><span class="sxs-lookup"><span data-stu-id="5ed4e-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ed4e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ed4e-118">See also</span></span>
- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="5ed4e-119">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="5ed4e-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="5ed4e-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="5ed4e-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="5ed4e-121">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="5ed4e-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
