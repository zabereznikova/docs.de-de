---
title: Verbinden mit einer Datenquelle in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 20cf22e1c9b9bf18dd3109cb9589c05a6c27d4d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701741"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="79efb-102">Verbinden mit einer Datenquelle in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79efb-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="79efb-103">In ADO.NET verwenden Sie eine **Verbindung** Objekt zur Verbindung mit einer bestimmten Datenquelle durch Angabe der erforderlichen Authentifizierungsinformationen in einer Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="79efb-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="79efb-104">Die **Verbindung** Objekt abhängig ist, auf dem Typ der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="79efb-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="79efb-105">Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="79efb-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79efb-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="79efb-106">In This Section</span></span>  
 [<span data-ttu-id="79efb-107">Herstellen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="79efb-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="79efb-108">Beschreibt, wie eine **Verbindung** Objekt zum Herstellen einer Verbindung mit einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="79efb-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="79efb-109">Verbindungsereignisse</span><span class="sxs-lookup"><span data-stu-id="79efb-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="79efb-110">Beschreibt, wie ein **InfoMessage** Ereignis informationsmeldungen aus einer Datenquelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="79efb-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79efb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79efb-111">See also</span></span>
- [<span data-ttu-id="79efb-112">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="79efb-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="79efb-113">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="79efb-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)
- [<span data-ttu-id="79efb-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="79efb-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="79efb-115">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="79efb-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="79efb-116">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="79efb-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [<span data-ttu-id="79efb-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="79efb-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
