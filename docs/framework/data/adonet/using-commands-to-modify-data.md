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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 70a83453eef990a03515a4860917f3c4d72599c3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="640da-102">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="640da-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="640da-103">Mit einem .NET Framework-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen-Anweisungen (z. B. CREATE TABLE und ALTER COLUMN) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="640da-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="640da-104">Mit diesen Befehlen werden keine Zeilen zurückgegeben, wie eine Abfrage der Fall wäre also die **Befehl** Objekt enthält ein **ExecuteNonQuery** verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="640da-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="640da-105">Zusätzlich zur Verwendung von **ExecuteNonQuery** Schema ändern, können Sie auch SQL-Anweisungen verarbeiten, die Daten ändern, aber, die nicht Zeilen zurückgeben, z. B. INSERT, UPDATE, und löschen Sie, diese Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="640da-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="640da-106">Obwohl Zeilen vom nicht zurückgegeben werden die **ExecuteNonQuery** -Methode, die Eingabeparameter, Ausgabeparameter und Rückgabewerte übergeben und zurückgegeben, die über die **Parameter** Auflistung von der **Befehl**  Objekt.</span><span class="sxs-lookup"><span data-stu-id="640da-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="640da-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="640da-107">In This Section</span></span>  
 [<span data-ttu-id="640da-108">Aktualisieren von Daten in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="640da-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="640da-109">Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="640da-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="640da-110">Ausführen von Katalogoperationen</span><span class="sxs-lookup"><span data-stu-id="640da-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="640da-111">Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.</span><span class="sxs-lookup"><span data-stu-id="640da-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640da-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="640da-112">See Also</span></span>  
 [<span data-ttu-id="640da-113">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="640da-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="640da-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="640da-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="640da-115">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="640da-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
