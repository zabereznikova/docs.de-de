---
title: Navigieren in "DataRelations"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 5eb2ee16712be5ccd5e9aa0af4dde22dcaaeea09
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148385"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="c534b-102">Navigieren in "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="c534b-102">Navigating DataRelations</span></span>

<span data-ttu-id="c534b-103">Eine der Hauptfunktionen einer <xref:System.Data.DataRelation> besteht darin, die Navigation von einer <xref:System.Data.DataTable> zu einer anderen innerhalb eines <xref:System.Data.DataSet> zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c534b-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c534b-104">Auf diese Weise können Sie alle verknüpften <xref:System.Data.DataRow> Objekte in einer **Daten** Tabelle abrufen, wenn Sie eine einzelne **DataRow** aus einer verknüpften **Daten**Tabelle erhalten.</span><span class="sxs-lookup"><span data-stu-id="c534b-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="c534b-105">Nachdem Sie z. b. eine **DataRelations** zwischen einer Tabelle mit Kunden und einer Tabelle mit Bestellungen eingerichtet haben, können Sie mithilfe von **GetChildRows**alle Auftragszeilen für eine bestimmte Kunden Zeile abrufen.</span><span class="sxs-lookup"><span data-stu-id="c534b-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="c534b-106">Im folgenden Codebeispiel wird eine **DataRelations** zwischen der **Customers** -Tabelle und der **Orders** -Tabelle eines **DataSets** erstellt und alle Bestellungen für jeden Kunden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c534b-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="c534b-107">Das nächste Beispiel baut auf dem vorhergehenden Beispiel auf. Hier werden vier Tabellen miteinander verknüpft, sodass über diese Beziehungen zu den Tabellen navigiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c534b-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="c534b-108">Wie im vorherigen Beispiel verknüpft **CustomerID** die **Customers** -Tabelle mit der **Orders** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c534b-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="c534b-109">Für jeden Kunden in der **Customers** -Tabelle werden alle untergeordneten Zeilen in der **Orders** -Tabelle bestimmt, um die Anzahl der Bestellungen eines bestimmten Kunden und deren **OrderID** -Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c534b-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="c534b-110">Das erweiterte Beispiel gibt auch die Werte aus den Tabellen **Order Details** und **Products** zurück.</span><span class="sxs-lookup"><span data-stu-id="c534b-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="c534b-111">Die **Orders** -Tabelle bezieht sich auf die **Order Details** -Tabelle mithilfe von **OrderID** , um für jeden Kundenauftrag festzustellen, welche Produkte und Mengen sortiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c534b-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="c534b-112">Da die **Order Details** -Tabelle nur die **ProductID** eines bestellten Produkts enthält, steht **Order Details** im Zusammenhang mit **Produkten** , die **ProductID** verwenden, um **ProductName**zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c534b-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="c534b-113">In dieser Beziehung ist die Tabelle " **Products** " das übergeordnete Element, und die Tabelle " **Order Details** " ist das untergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="c534b-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="c534b-114">Daher wird beim Durchlaufen der **Order Details** -Tabelle **getparameentrow** aufgerufen, um den zugehörigen **ProductName** -Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c534b-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="c534b-115">Beachten Sie, dass bei der Erstellung der **DataRelations** -Tabelle für die **Customers** -und **Orders** -Tabelle kein Wert für das Flag "" vom Typ " **anateconstraints** " angegeben wird (Standardwert: **true**).</span><span class="sxs-lookup"><span data-stu-id="c534b-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="c534b-116">Dabei wird davon ausgegangen, dass alle Zeilen in der **Orders** -Tabelle einen **CustomerID-** Wert aufweisen, der in der übergeordneten **Customers** -Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c534b-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="c534b-117">Wenn eine **CustomerID** in der **Orders** -Tabelle vorhanden ist, die in der **Customers** -Tabelle nicht vorhanden ist, <xref:System.Data.ForeignKeyConstraint> wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c534b-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="c534b-118">Wenn die untergeordnete Spalte Werte enthalten kann, die in der übergeordneten Spalte nicht enthalten sind, legen Sie beim Hinzufügen von **DataRelations**das Flag " **kreateconstraints** " auf " **false** " fest.</span><span class="sxs-lookup"><span data-stu-id="c534b-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="c534b-119">In dem Beispiel wird das Flag " **kreateconstraints** " für " **DataRelations** " zwischen der Tabelle " **Orders** " und der Tabelle " **Order Details** " auf " **false** " festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c534b-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="c534b-120">Dadurch kann die Anwendung alle Datensätze aus der Tabelle **Order Details** und nur eine Teilmenge der Datensätze aus der Tabelle **Orders** zurückgeben, ohne eine Lauf Zeit Ausnahme zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="c534b-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="c534b-121">Im erweiterten Beispiel wird die Ausgabe im folgenden Format generiert:</span><span class="sxs-lookup"><span data-stu-id="c534b-121">The expanded sample generates output in the following format.</span></span>  
  
```output  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="c534b-122">Das folgende Codebeispiel ist ein erweitertes Beispiel, bei dem die Werte aus den Tabellen **Order Details** und **Products** zurückgegeben werden, wobei nur eine Teilmenge der Datensätze in der **Orders** -Tabelle zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c534b-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c534b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c534b-123">See also</span></span>

- [<span data-ttu-id="c534b-124">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="c534b-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c534b-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c534b-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
