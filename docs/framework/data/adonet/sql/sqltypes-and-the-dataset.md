---
title: "\"SqlTypes\" und \"DataSet\""
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
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 86132e266b4421cce048ea38fc91967267a6ae6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="30a1e-102">"SqlTypes" und "DataSet"</span><span class="sxs-lookup"><span data-stu-id="30a1e-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="30a1e-103">Mit ADO.NET 2.0 wurde eine erweiterte Typunterstützung für das `DataSet` durch den <xref:System.Data.SqlTypes>-Namespace eingeführt.</span><span class="sxs-lookup"><span data-stu-id="30a1e-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="30a1e-104">Die Typen in <xref:System.Data.SqlTypes> stellen Datentypen mit derselben Semantik und Präzision wie die Datentypen in einer SQL Server-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="30a1e-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="30a1e-105">Für jeden Datentyp in <xref:System.Data.SqlTypes> gibt es einen äquivalenten Datentyp in SQL Server mit derselben zugrunde liegenden Datendarstellung.</span><span class="sxs-lookup"><span data-stu-id="30a1e-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="30a1e-106">Die direkte Verwendung von <xref:System.Data.SqlTypes> in einem <xref:System.Data.DataSet> beim Arbeiten mit SQL Server-Datentypen hat mehrere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="30a1e-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="30a1e-107"><xref:System.Data.SqlTypes> unterstützt die gleiche Semantik wie systemeigene SQL Server-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="30a1e-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="30a1e-108">Bei Angabe eines <xref:System.Data.SqlTypes> in der Definition eines <xref:System.Data.DataColumn>-Objekts wird der Verlust an Genauigkeit ausgeglichen, die auftreten kann, wenn Dezimaldatentypen oder numerische Datentypen zu einem Datentyp der Common Language Runtime (CLR) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="30a1e-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30a1e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30a1e-109">Example</span></span>  
 <span data-ttu-id="30a1e-110">Im folgenden Beispiel wird ein <xref:System.Data.DataTable>-Objekt erstellt. Dabei werden explizit die <xref:System.Data.DataColumn>-Datentypen definiert, wobei anstelle von CLR-Typen <xref:System.Data.SqlTypes> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30a1e-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="30a1e-111">Der Code füllt die <xref:System.Data.DataTable> mit Daten aus der Sales.SalesOrderDetail-Tabelle in der SQL Server-AdventureWorks-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="30a1e-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="30a1e-112">In der Ausgabe im Konsolenfenster werden der Datentyp der einzelnen Spalten und die von SQL Server abgerufenen Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30a1e-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="30a1e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30a1e-113">See Also</span></span>  
 [<span data-ttu-id="30a1e-114">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="30a1e-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="30a1e-115">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="30a1e-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="30a1e-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="30a1e-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
