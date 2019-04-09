---
title: "\"SqlTypes\" und \"DataSet\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: a218a8e0fe3d2c17a0f09a40645c7b3ad26fb5ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072700"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="b8921-102">"SqlTypes" und "DataSet"</span><span class="sxs-lookup"><span data-stu-id="b8921-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="b8921-103">Mit ADO.NET 2.0 wurde eine erweiterte Typunterstützung für das `DataSet` durch den <xref:System.Data.SqlTypes>-Namespace eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b8921-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="b8921-104">Die Typen in <xref:System.Data.SqlTypes> stellen Datentypen mit derselben Semantik und Präzision wie die Datentypen in einer SQL Server-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="b8921-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="b8921-105">Für jeden Datentyp in <xref:System.Data.SqlTypes> gibt es einen äquivalenten Datentyp in SQL Server mit derselben zugrunde liegenden Datendarstellung.</span><span class="sxs-lookup"><span data-stu-id="b8921-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="b8921-106">Die direkte Verwendung von <xref:System.Data.SqlTypes> in einem <xref:System.Data.DataSet> beim Arbeiten mit SQL Server-Datentypen hat mehrere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="b8921-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <xref:System.Data.SqlTypes> <span data-ttu-id="b8921-107">unterstützt die gleiche Semantik wie systemeigene SQL Server-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="b8921-107">supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="b8921-108">Bei Angabe eines <xref:System.Data.SqlTypes> in der Definition eines <xref:System.Data.DataColumn>-Objekts wird der Verlust an Genauigkeit ausgeglichen, die auftreten kann, wenn Dezimaldatentypen oder numerische Datentypen zu einem Datentyp der Common Language Runtime (CLR) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8921-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8921-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8921-109">Example</span></span>  
 <span data-ttu-id="b8921-110">Im folgenden Beispiel wird ein <xref:System.Data.DataTable>-Objekt erstellt. Dabei werden explizit die <xref:System.Data.DataColumn>-Datentypen definiert, wobei anstelle von CLR-Typen <xref:System.Data.SqlTypes> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8921-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="b8921-111">Der Code füllt die <xref:System.Data.DataTable> mit Daten aus der Sales.SalesOrderDetail-Tabelle in der SQL Server-AdventureWorks-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b8921-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="b8921-112">In der Ausgabe im Konsolenfenster werden der Datentyp der einzelnen Spalten und die von SQL Server abgerufenen Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8921-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b8921-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8921-113">See also</span></span>

- [<span data-ttu-id="b8921-114">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="b8921-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="b8921-115">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="b8921-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="b8921-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b8921-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
