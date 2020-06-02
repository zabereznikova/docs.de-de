---
title: Verbindungspooling
description: Erfahren Sie mehr über das Verbindungspooling, eine Optimierungstechnik, mit der ADO.net die Kosten für das Öffnen von Verbindungen mit Datenquellen minimiert.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: b8f89dfda7edbde14dbb5945f10f2284ac43c3d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287089"
---
# <a name="connection-pooling"></a><span data-ttu-id="9e05f-103">Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="9e05f-103">Connection Pooling</span></span>
<span data-ttu-id="9e05f-104">Das Herstellen einer Verbindung mit einer Datenquelle kann viel Zeit kosten.</span><span class="sxs-lookup"><span data-stu-id="9e05f-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="9e05f-105">Um die Kosten für das Öffnen von Verbindungen zu minimieren, verwendet ADO.net eine Optimierungstechnik, die als *Verbindungspooling*bezeichnet wird und die Kosten für das wiederholte öffnen und Schließen von Verbindungen minimiert.</span><span class="sxs-lookup"><span data-stu-id="9e05f-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="9e05f-106">Das Verbindungspooling wird bei den einzelnen .NET Framework-Datenanbietern unterschiedlich gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="9e05f-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e05f-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9e05f-107">In This Section</span></span>  
 [<span data-ttu-id="9e05f-108">SQL Server-Verbindungspooling (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="9e05f-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="9e05f-109">Bietet eine Übersicht über das Verbindungspooling und beschreibt, wie das Verbindungspooling in SQL Server funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9e05f-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="9e05f-110">OLE DB-, ODBC- und Oracle-Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="9e05f-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="9e05f-111">Beschreibt das Verbindungspooling für den .NET Framework-Datenanbieter für OLE DB, den .NET Framework-Datenanbieter für ODBC und den .NET Framework-Datenanbieter für Oracle.</span><span class="sxs-lookup"><span data-stu-id="9e05f-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e05f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e05f-112">See also</span></span>

- [<span data-ttu-id="9e05f-113">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e05f-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="9e05f-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e05f-114">ADO.NET Overview</span></span>](ado-net-overview.md)
