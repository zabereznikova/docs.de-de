---
title: Benutzerdefinierte CLR-Typen
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: 4ea415a348375c52e42ddf26ea09a74e7de5e355
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45673765"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="681e8-102">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="681e8-102">CLR User-Defined Types</span></span>
<span data-ttu-id="681e8-103">Microsoft SQL Server bietet Unterstützung für benutzerdefinierte Typen (User-Defined Types, UDTs), die mit der CLR (Common Language Runtime) von Microsoft .NET Framework implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="681e8-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="681e8-104">Durch die Integration der CLR in SQL Server verfügen Sie über einen Mechanismus, mit dessen Hilfe Sie das Typsystem der Datenbank erweitern können.</span><span class="sxs-lookup"><span data-stu-id="681e8-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="681e8-105">UDTs ermöglichen neben der Erweiterbarkeit des SQL Server-Datentypsystems durch Benutzer auch das Definieren komplexer strukturierter Typen.</span><span class="sxs-lookup"><span data-stu-id="681e8-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="681e8-106">UDTs bieten im Hinblick auf die Anwendungsarchitektur zwei wesentliche Vorteile:</span><span class="sxs-lookup"><span data-stu-id="681e8-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="681e8-107">Starke Kapselung von internem Zustand gegenüber externen Verhaltensweisen (sowohl auf dem Client als auch auf dem Server).</span><span class="sxs-lookup"><span data-stu-id="681e8-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="681e8-108">Enge Integration mit anderen verwandten Serverfunktionen.</span><span class="sxs-lookup"><span data-stu-id="681e8-108">Deep integration with other related server features.</span></span> <span data-ttu-id="681e8-109">Nachdem Sie einen eigenen UDT definiert haben, kann dieser in den gleichen Kontexten verwendet werden wie ein Systemtyp von SQL Server, so u. a. als Spaltendefinitionen, Variablen, Parameter, Funktionsergebnisse, Cursor, Trigger und bei der Replikation.</span><span class="sxs-lookup"><span data-stu-id="681e8-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="681e8-110">Weitere Informationen finden Sie unter den [SQL Server-Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="681e8-110">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="681e8-111">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="681e8-111">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="681e8-112">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="681e8-112">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="681e8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="681e8-113">See also</span></span>  

[<span data-ttu-id="681e8-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="681e8-114">ADO.NET Overview</span></span>](../ado-net-overview.md)  