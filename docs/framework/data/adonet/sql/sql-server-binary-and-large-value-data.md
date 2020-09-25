---
title: Binäre Daten und Daten mit umfangreichen Werten in SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183038"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="102b5-102">Binäre Daten und Daten mit umfangreichen Werten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="102b5-102">SQL Server Binary and Large-Value Data</span></span>

<span data-ttu-id="102b5-103">SQL Server stellt den `max`-Spezifizierer bereit, der die Speicherkapazität der Datentypen `varchar`, `nvarchar` und `varbinary` erweitert.</span><span class="sxs-lookup"><span data-stu-id="102b5-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="102b5-104">`varchar(max)`, `nvarchar(max)` und `varbinary(max)` werden zusammenfassend als *Datentypen mit umfangreichen Werten* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="102b5-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="102b5-105">Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31-1 Bytes an Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="102b5-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="102b5-106">In SQL Server 2008 wurde das FILESTREAM-Attribut eingeführt, das kein Datentyp ist. Es ist ein Attribut, das für eine Spalte definiert werden kann, wodurch Daten mit umfangreichen Werten im Dateisystem anstatt in der Datenbank gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="102b5-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="102b5-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="102b5-107">In This Section</span></span>  

 [<span data-ttu-id="102b5-108">Ändern von Daten mit umfangreichen Werten (max) in ADO.net</span><span class="sxs-lookup"><span data-stu-id="102b5-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="102b5-109">Beschreibt das Arbeiten mit den Datentypen für große Werte.</span><span class="sxs-lookup"><span data-stu-id="102b5-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="102b5-110">FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="102b5-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="102b5-111">Beschreibt, wie Sie mit Daten mit großen Werten arbeiten, die in SQL Server 2008 mit dem FILESTREAM-Attribut gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="102b5-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102b5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="102b5-112">See also</span></span>

- [<span data-ttu-id="102b5-113">SQL Server-Datentypen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="102b5-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="102b5-114">SQL Server von Daten Vorgängen in ADO.net</span><span class="sxs-lookup"><span data-stu-id="102b5-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="102b5-115">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="102b5-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="102b5-116">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="102b5-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
