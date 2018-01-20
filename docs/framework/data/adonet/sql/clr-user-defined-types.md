---
title: Benutzerdefinierte CLR-Typen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ed299dd91b16815cbbb50cd51602bb0161ec6939
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="c40b8-102">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="c40b8-102">CLR User-Defined Types</span></span>
<span data-ttu-id="c40b8-103">Microsoft SQL Server bietet Unterstützung für benutzerdefinierte Typen (User-Defined Types, UDTs), die mit der CLR (Common Language Runtime) von Microsoft .NET Framework implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="c40b8-103">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="c40b8-104">Durch die Integration der CLR in SQL Server verfügen Sie über einen Mechanismus, mit dessen Hilfe Sie das Typsystem der Datenbank erweitern können.</span><span class="sxs-lookup"><span data-stu-id="c40b8-104">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="c40b8-105">UDTs ermöglichen neben der Erweiterbarkeit des SQL Server-Datentypsystems durch Benutzer auch das Definieren komplexer strukturierter Typen.</span><span class="sxs-lookup"><span data-stu-id="c40b8-105">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="c40b8-106">UDTs bieten im Hinblick auf die Anwendungsarchitektur zwei wesentliche Vorteile:</span><span class="sxs-lookup"><span data-stu-id="c40b8-106">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
-   <span data-ttu-id="c40b8-107">Starke Kapselung von internem Zustand gegenüber externen Verhaltensweisen (sowohl auf dem Client als auch auf dem Server).</span><span class="sxs-lookup"><span data-stu-id="c40b8-107">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
-   <span data-ttu-id="c40b8-108">Enge Integration mit anderen verwandten Serverfunktionen.</span><span class="sxs-lookup"><span data-stu-id="c40b8-108">Deep integration with other related server features.</span></span> <span data-ttu-id="c40b8-109">Nachdem Sie einen eigenen UDT definiert haben, kann dieser in den gleichen Kontexten verwendet werden wie ein Systemtyp von SQL Server, so u. a. als Spaltendefinitionen, Variablen, Parameter, Funktionsergebnisse, Cursor, Trigger und bei der Replikation.</span><span class="sxs-lookup"><span data-stu-id="c40b8-109">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="c40b8-110">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c40b8-110">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="c40b8-111">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="c40b8-111">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="c40b8-112">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="c40b8-112">CLR User-Defined Types</span></span>](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a><span data-ttu-id="c40b8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c40b8-113">See Also</span></span>  
 [<span data-ttu-id="c40b8-114">Erstellen von SQL Server 2005-Objekte In verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="c40b8-114">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="c40b8-115">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c40b8-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
