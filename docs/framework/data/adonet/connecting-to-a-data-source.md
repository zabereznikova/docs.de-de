---
title: Verbinden mit einer Datenquelle in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 01e4048fb9c7b53b1b1907d1965f822b9a4644a4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786767"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="e1f10-102">Verbinden mit einer Datenquelle in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1f10-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="e1f10-103">In ADO.NET verwenden Sie ein **Verbindungs** Objekt, um eine Verbindung mit einer bestimmten Datenquelle herzustellen, indem Sie die erforderlichen Authentifizierungsinformationen in einer Verbindungs Zeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e1f10-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="e1f10-104">Welches **Verbindungs** Objekt Sie verwenden, hängt vom Typ der Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="e1f10-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="e1f10-105">Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>-Objekt: Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e1f10-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1f10-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e1f10-106">In This Section</span></span>  
 [<span data-ttu-id="e1f10-107">Herstellen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="e1f10-107">Establishing the Connection</span></span>](establishing-the-connection.md)  
 <span data-ttu-id="e1f10-108">Beschreibt, wie ein **Verbindungs** Objekt verwendet wird, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e1f10-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="e1f10-109">Verbindungsereignisse</span><span class="sxs-lookup"><span data-stu-id="e1f10-109">Connection Events</span></span>](connection-events.md)  
 <span data-ttu-id="e1f10-110">Beschreibt, wie ein **infomess** -Ereignis zum Abrufen von Informationsmeldungen aus einer Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1f10-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f10-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1f10-111">See also</span></span>

- [<span data-ttu-id="e1f10-112">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e1f10-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="e1f10-113">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="e1f10-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="e1f10-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="e1f10-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="e1f10-115">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="e1f10-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="e1f10-116">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="e1f10-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="e1f10-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1f10-117">ADO.NET Overview</span></span>](ado-net-overview.md)
