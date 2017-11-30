---
title: "Verwenden von Befehlen zum Ändern von Daten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 853f8e4e75df3fffad4a2d5ecd4f7ae21b5d674f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="6f0e0-102">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="6f0e0-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="6f0e0-103">Mit einem .NET Framework-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen-Anweisungen (z. B. CREATE TABLE und ALTER COLUMN) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="6f0e0-104">Mit diesen Befehlen werden keine Zeilen zurückgegeben, wie eine Abfrage der Fall wäre also die **Befehl** Objekt enthält ein **ExecuteNonQuery** verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="6f0e0-105">Zusätzlich zur Verwendung von **ExecuteNonQuery** Schema ändern, können Sie auch SQL-Anweisungen verarbeiten, die Daten ändern, aber, die nicht Zeilen zurückgeben, z. B. INSERT, UPDATE, und löschen Sie, diese Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="6f0e0-106">Obwohl Zeilen vom nicht zurückgegeben werden die **ExecuteNonQuery** -Methode, die Eingabeparameter, Ausgabeparameter und Rückgabewerte übergeben und zurückgegeben, die über die **Parameter** Auflistung von der **Befehl**  Objekt.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f0e0-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6f0e0-107">In This Section</span></span>  
 [<span data-ttu-id="6f0e0-108">Aktualisieren von Daten in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="6f0e0-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="6f0e0-109">Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="6f0e0-110">Ausführen von Katalogoperationen</span><span class="sxs-lookup"><span data-stu-id="6f0e0-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="6f0e0-111">Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6f0e0-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0e0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f0e0-112">See Also</span></span>  
 [<span data-ttu-id="6f0e0-113">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f0e0-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="6f0e0-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="6f0e0-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="6f0e0-115">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="6f0e0-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
