---
title: "\"SqlTypes\" und \"DataSet\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 04f95cd7d3f6e52f644f23dd8a32c77d56a5ddda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147507"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="3e5ba-102">"SqlTypes" und "DataSet"</span><span class="sxs-lookup"><span data-stu-id="3e5ba-102">SqlTypes and the DataSet</span></span>

<span data-ttu-id="3e5ba-103">Mit ADO.NET 2.0 wurde durch den Namespace <xref:System.Data.SqlTypes> erweiterte Typunterstützung für das `DataSet` eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="3e5ba-104">Die Typen in <xref:System.Data.SqlTypes> stellen Datentypen mit derselben Semantik und Präzision wie die Datentypen in einer SQL Server-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="3e5ba-105">Für jeden Datentyp in <xref:System.Data.SqlTypes> gibt es einen äquivalenten Datentyp in SQL Server mit derselben zugrunde liegenden Datendarstellung.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="3e5ba-106">Wenn Sie <xref:System.Data.SqlTypes> direkt in einem <xref:System.Data.DataSet> verwenden, profitieren Sie von einigen Vorteilen bei der Arbeit mit SQL Server-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="3e5ba-107"><xref:System.Data.SqlTypes> unterstützt die gleiche Semantik wie native SQL Server-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="3e5ba-108">Wenn Sie einen <xref:System.Data.SqlTypes>-Namespace in der Definition einer <xref:System.Data.DataColumn>-Klasse angeben, ist dies präziser als die Konvertierung von dezimalen oder numerische Datentypen in einen CLR-Datentyp (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="3e5ba-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e5ba-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e5ba-109">Example</span></span>  

 <span data-ttu-id="3e5ba-110">Im folgenden Beispiel wird ein <xref:System.Data.DataTable>-Objekt erstellt. Dabei werden explizit die <xref:System.Data.DataColumn>-Datentypen definiert, wobei anstelle von CLR-Typen <xref:System.Data.SqlTypes> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="3e5ba-111">Der Code füllt die <xref:System.Data.DataTable> mit Daten aus der Sales.SalesOrderDetail-Tabelle in der SQL Server-AdventureWorks-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="3e5ba-112">Die im Konsolenfenster angezeigte Ausgabe enthält die Datentypen der einzelnen Spalten und die von SQL Server abgerufenen Werte.</span><span class="sxs-lookup"><span data-stu-id="3e5ba-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3e5ba-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e5ba-113">See also</span></span>

- [<span data-ttu-id="3e5ba-114">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="3e5ba-114">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="3e5ba-115">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="3e5ba-115">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="3e5ba-116">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3e5ba-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
