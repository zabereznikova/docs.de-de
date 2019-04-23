---
title: Verbindungspooling
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: 4cba53993489f51ed39ac52bff4fa252beb9aafd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180452"
---
# <a name="connection-pooling"></a><span data-ttu-id="7de01-102">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="7de01-102">Connection Pooling</span></span>
<span data-ttu-id="7de01-103">Das Herstellen einer Verbindung mit einer Datenquelle kann viel Zeit kosten.</span><span class="sxs-lookup"><span data-stu-id="7de01-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="7de01-104">Um die Kosten für das Herstellen von Verbindungen zu reduzieren, verwendet ADO.NET eine Optimierungstechnik, die Namen *Verbindungspooling*, die die Kosten für das wiederholte öffnen und Schließen von Verbindungen minimiert.</span><span class="sxs-lookup"><span data-stu-id="7de01-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="7de01-105">Das Verbindungspooling wird bei den einzelnen .NET Framework-Datenanbietern unterschiedlich gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="7de01-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7de01-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7de01-106">In This Section</span></span>  
 [<span data-ttu-id="7de01-107">SQL Server-Verbindungspooling (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="7de01-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="7de01-108">Bietet einen Überblick über das Verbindungspooling und beschreibt, wie das Verbindungspooling in SQL Server funktioniert.</span><span class="sxs-lookup"><span data-stu-id="7de01-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="7de01-109">OLE DB-, ODBC- und Oracle-Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="7de01-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="7de01-110">Beschreibt das Verbindungspooling für den .NET Framework-Datenanbieter für OLE DB, den .NET Framework-Datenanbieter für ODBC und den .NET Framework-Datenanbieter für Oracle.</span><span class="sxs-lookup"><span data-stu-id="7de01-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de01-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7de01-111">See also</span></span>

- [<span data-ttu-id="7de01-112">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7de01-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="7de01-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7de01-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
