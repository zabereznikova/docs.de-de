---
title: 'Vorgehensweise: Implementieren von CopyToDataTable&lt;T&gt; , in dem der generische Typ T ist keiner DataRow'
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
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 44e54ef54173636246da1847d177cf4fd99ea818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-copytodatatablelttgt-where-the-generic-type-t-is-not-a-datarow"></a><span data-ttu-id="89d75-102">Vorgehensweise: Implementieren von CopyToDataTable&lt;T&gt; , in dem der generische Typ T ist keiner DataRow</span><span class="sxs-lookup"><span data-stu-id="89d75-102">How to: Implement CopyToDataTable&lt;T&gt; Where the Generic Type T Is Not a DataRow</span></span>
<span data-ttu-id="89d75-103">Das <xref:System.Data.DataTable>-Objekt wird oft für die Datenbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="89d75-103">The <xref:System.Data.DataTable> object is often used for data binding.</span></span> <span data-ttu-id="89d75-104">Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode kopiert die Ergebnisse einer Abfrage in eine <xref:System.Data.DataTable>, die dann für die Datenbindung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="89d75-104">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="89d75-105">Die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methoden arbeiten allerdings nur mit einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle, bei der der generische Parameter `T` den Typ <xref:System.Data.DataRow> aufweist.</span><span class="sxs-lookup"><span data-stu-id="89d75-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods, however, only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="89d75-106">Obwohl dies hilfreich ist, können Tabellen dabei nicht aus einer Sequenz von Skalartypen, aus Abfragen, die anonyme Typen darstellen oder aus Abfragen, die Tabellenjoins durchführen, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="89d75-106">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that project anonymous types, or from queries that perform table joins.</span></span>  
  
 <span data-ttu-id="89d75-107">In diesem Thema wird beschrieben, wie zwei benutzerdefinierte `CopyToDataTable<T>`-Erweiterungsmethoden implementiert werden, die einen generischen Parameter `T` annehmen, der einen anderen Typ als <xref:System.Data.DataRow> aufweist.</span><span class="sxs-lookup"><span data-stu-id="89d75-107">This topic describes how to implement two custom `CopyToDataTable<T>` extension methods that accept a generic parameter `T` of a type other than <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="89d75-108">Die Logik zum Erstellen einer <xref:System.Data.DataTable> aus einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle ist in der `ObjectShredder<T>`-Klasse enthalten, die wiederum von zwei überladenen `CopyToDataTable<T>`-Erweiterungsmethoden umschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="89d75-108">The logic to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source is contained in the `ObjectShredder<T>` class, which is then wrapped in two overloaded `CopyToDataTable<T>` extension methods.</span></span> <span data-ttu-id="89d75-109">Die `Shred`-Methode der `ObjectShredder<T>`-Klasse gibt die gefüllte <xref:System.Data.DataTable> zurück und nimmt drei Eingabeparameter an: eine <xref:System.Collections.Generic.IEnumerable%601>-Quelle, eine <xref:System.Data.DataTable> und eine <xref:System.Data.LoadOption>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="89d75-109">The `Shred` method of the `ObjectShredder<T>` class returns the filled <xref:System.Data.DataTable> and accepts three input parameters: an <xref:System.Collections.Generic.IEnumerable%601> source, a <xref:System.Data.DataTable>, and a <xref:System.Data.LoadOption> enumeration.</span></span> <span data-ttu-id="89d75-110">Das anfängliche Schema der zurückgegebenen <xref:System.Data.DataTable> basiert auf dem Schema des Typs `T`.</span><span class="sxs-lookup"><span data-stu-id="89d75-110">The initial schema of the returned <xref:System.Data.DataTable> is based on the schema of the type `T`.</span></span> <span data-ttu-id="89d75-111">Wenn eine vorhandene Tabelle als Eingabe bereitgestellt wird, muss deren Schema mit dem Schema des Typs `T` übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="89d75-111">If an existing table is provided as input, the schema must be consistent with the schema of the type `T`.</span></span> <span data-ttu-id="89d75-112">Jede öffentliche Eigenschaft und jedes Feld des Typs `T` wird in eine <xref:System.Data.DataColumn> in der zurückgegebenen Tabelle konvertiert.</span><span class="sxs-lookup"><span data-stu-id="89d75-112">Each public property and field of the type `T` is converted to a <xref:System.Data.DataColumn> in the returned table.</span></span> <span data-ttu-id="89d75-113">Wenn die Quellsequenz einen von `T` abgeleiteten Typ enthält, wird das zurückgegebene Tabellenschema um zusätzliche öffentliche Eigeschaften bzw. Felder erweitert.</span><span class="sxs-lookup"><span data-stu-id="89d75-113">If the source sequence contains a type derived from `T`, the returned table schema is expanded for any additional public properties or fields.</span></span>  
  
 <span data-ttu-id="89d75-114">Beispiele für die Verwendung der benutzerdefinierten `CopyToDataTable<T>` Methoden, finden Sie unter [Erstellen einer DataTable aus einer Abfrage](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="89d75-114">For examples of using the custom `CopyToDataTable<T>` methods, see [Creating a DataTable From a Query](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).</span></span>  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a><span data-ttu-id="89d75-115">Zum Implementieren von benutzerdefinierten CopyToDataTable\<T > Methoden in Ihrer Anwendung</span><span class="sxs-lookup"><span data-stu-id="89d75-115">To implement the custom CopyToDataTable\<T> methods in your application</span></span>  
  
1.  <span data-ttu-id="89d75-116">Implementieren Sie die `ObjectShredder<T>`-Klasse, um eine <xref:System.Data.DataTable> aus einer <xref:System.Collections.Generic.IEnumerable%601>-Quelle zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="89d75-116">Implement the `ObjectShredder<T>` class to create a <xref:System.Data.DataTable> from an <xref:System.Collections.Generic.IEnumerable%601> source:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  
  
2.  <span data-ttu-id="89d75-117">Implementieren Sie die benutzerdefinierten `CopyToDataTable<T>`-Erweiterungsmethoden in einer Klasse:</span><span class="sxs-lookup"><span data-stu-id="89d75-117">Implement the custom `CopyToDataTable<T>` extension methods in a class:</span></span>  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3.  <span data-ttu-id="89d75-118">Fügen Sie die `ObjectShredder<T>`-Klasse und die `CopyToDataTable<T>`-Erweiterungsmethoden Ihrer Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="89d75-118">Add the `ObjectShredder<T>` class and `CopyToDataTable<T>` extension methods to your application.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="89d75-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89d75-119">See Also</span></span>  
 [<span data-ttu-id="89d75-120">Erstellen einer "DataTable" aus einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="89d75-120">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 [<span data-ttu-id="89d75-121">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="89d75-121">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
