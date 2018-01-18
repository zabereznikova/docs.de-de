---
title: Erstellen von Ausdrucksspalten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 03c049ea3fb4b0f75418de4f9e8318512c198f41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="creating-expression-columns"></a><span data-ttu-id="f7b61-102">Erstellen von Ausdrucksspalten</span><span class="sxs-lookup"><span data-stu-id="f7b61-102">Creating Expression Columns</span></span>
<span data-ttu-id="f7b61-103">Sie können einen Ausdruck für eine Spalte definieren, sodass diese einen Wert enthalten kann, der aus anderen Spaltenwerten in der gleichen Zeile oder aus Spaltenwerten mehrerer Zeilen in der Tabelle berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="f7b61-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="f7b61-104">Wenn Sie den auszuwertenden Ausdruck definieren möchten, verwenden Sie die <xref:System.Data.DataColumn.Expression%2A>-Eigenschaft der Zielspalte und verweisen mithilfe der <xref:System.Data.DataColumn.ColumnName%2A>-Eigenschaft auf andere Spalten im Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f7b61-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="f7b61-105">Der <xref:System.Data.DataColumn.DataType%2A> für die Ausdrucksspalte muss für den Wert geeignet sein, den der Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f7b61-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="f7b61-106">In der folgenden Tabelle werden Verwendungsmöglichkeiten für Ausdrucksspalten in einer Tabelle aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f7b61-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="f7b61-107">Ausdruckstyp</span><span class="sxs-lookup"><span data-stu-id="f7b61-107">Expression type</span></span>|<span data-ttu-id="f7b61-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7b61-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="f7b61-109">Vergleich</span><span class="sxs-lookup"><span data-stu-id="f7b61-109">Comparison</span></span>|<span data-ttu-id="f7b61-110">"Gesamtsumme >= 500"</span><span class="sxs-lookup"><span data-stu-id="f7b61-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="f7b61-111">Berechnung</span><span class="sxs-lookup"><span data-stu-id="f7b61-111">Computation</span></span>|<span data-ttu-id="f7b61-112">"Einzelpreis \* Menge"</span><span class="sxs-lookup"><span data-stu-id="f7b61-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="f7b61-113">Aggregation</span><span class="sxs-lookup"><span data-stu-id="f7b61-113">Aggregation</span></span>|<span data-ttu-id="f7b61-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="f7b61-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="f7b61-115">Sie können festlegen, die **Ausdruck** -Eigenschaft für ein vorhandenes **DataColumn** -Objekt, oder Sie zählen die Eigenschaft als dritte Argument übergeben der <xref:System.Data.DataColumn> Konstruktor, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7b61-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="f7b61-116">Ausdrücke können auf andere Ausdrucksspalten verweisen. Ein Zirkelverweis, bei dem zwei Ausdrücke aufeinander verweisen, generiert jedoch eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f7b61-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="f7b61-117">Regeln zum Schreiben von Ausdrücken finden Sie unter der <xref:System.Data.DataColumn.Expression%2A> Eigenschaft von der **DataColumn** Klasse.</span><span class="sxs-lookup"><span data-stu-id="f7b61-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b61-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7b61-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="f7b61-119">DataTable-Schemadefinition</span><span class="sxs-lookup"><span data-stu-id="f7b61-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="f7b61-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="f7b61-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="f7b61-121">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f7b61-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
