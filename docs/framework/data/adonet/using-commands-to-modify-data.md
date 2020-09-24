---
title: Verwenden von Befehlen zum Ändern von Daten
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: e2f61dbf74f28d026ae91a2bc8f5bb78530ffeac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177253"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="4bc82-102">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="4bc82-102">Using Commands to Modify Data</span></span>

<span data-ttu-id="4bc82-103">Mit einem .NET Framework-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen-Anweisungen (z. B. CREATE TABLE und ALTER COLUMN) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4bc82-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="4bc82-104">Diese Befehle geben keine Zeilen als Abfrage zurück, sodass das **Command** -Objekt eine **ExecuteNonQuery** zur Verarbeitung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4bc82-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="4bc82-105">Zusätzlich zur Verwendung von **ExecuteNonQuery** zum Ändern des Schemas können Sie diese Methode auch verwenden, um SQL-Anweisungen zu verarbeiten, die Daten ändern, aber keine Zeilen zurückgeben, wie z. b. Insert, Update und DELETE.</span><span class="sxs-lookup"><span data-stu-id="4bc82-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="4bc82-106">Obwohl Zeilen von der **ExecuteNonQuery** -Methode nicht zurückgegeben werden, können Eingabe-und Ausgabeparameter und Rückgabewerte über die **Parameters** -Auflistung des **Command** -Objekts übermittelt und zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4bc82-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bc82-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4bc82-107">In This Section</span></span>  

 [<span data-ttu-id="4bc82-108">Aktualisieren von Daten in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="4bc82-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="4bc82-109">Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4bc82-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="4bc82-110">Ausführen von Katalogoperationen</span><span class="sxs-lookup"><span data-stu-id="4bc82-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="4bc82-111">Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4bc82-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc82-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bc82-112">See also</span></span>

- [<span data-ttu-id="4bc82-113">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4bc82-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="4bc82-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="4bc82-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="4bc82-115">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4bc82-115">ADO.NET Overview</span></span>](ado-net-overview.md)
