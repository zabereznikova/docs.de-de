---
title: Verbinden mit einer Datenquelle in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: f5788b9b0b19f32d03c917575db7b3f40324c0a2
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706397"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="f04e0-102">Verbinden mit einer Datenquelle in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f04e0-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="f04e0-103">In ADO.NET verwenden Sie eine **Verbindung** Objekt zur Verbindung mit einer bestimmten Datenquelle durch Angabe der erforderlichen Authentifizierungsinformationen in einer Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f04e0-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="f04e0-104">Die **Verbindung** Objekt abhängig ist, auf dem Typ der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f04e0-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="f04e0-105">Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f04e0-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f04e0-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f04e0-106">In This Section</span></span>  
 [<span data-ttu-id="f04e0-107">Herstellen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="f04e0-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="f04e0-108">Beschreibt, wie eine **Verbindung** Objekt zum Herstellen einer Verbindung mit einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f04e0-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="f04e0-109">Verbindungsereignisse</span><span class="sxs-lookup"><span data-stu-id="f04e0-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="f04e0-110">Beschreibt, wie ein **InfoMessage** Ereignis informationsmeldungen aus einer Datenquelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="f04e0-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04e0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f04e0-111">See Also</span></span>  
 [<span data-ttu-id="f04e0-112">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f04e0-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="f04e0-113">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="f04e0-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="f04e0-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="f04e0-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="f04e0-115">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="f04e0-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="f04e0-116">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="f04e0-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="f04e0-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f04e0-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
