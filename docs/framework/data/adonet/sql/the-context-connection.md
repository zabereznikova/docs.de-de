---
title: Kontextverbindungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 40aa71a16c7a0616cfcf318901858da7587fa20b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="the-context-connection"></a><span data-ttu-id="c9237-102">Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="c9237-102">The Context Connection</span></span>
<span data-ttu-id="c9237-103">Das Problem des internen Datenzugriffs ist ein gängiges Szenario.</span><span class="sxs-lookup"><span data-stu-id="c9237-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="c9237-104">Dabei möchten Sie auf denselben Server zugreifen, auf dem die gespeicherte CLR-Prozedur oder CLR-Funktion (Common Language Runtime) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9237-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="c9237-105">Eine Option liegt darin, mithilfe von <xref:System.Data.SqlClient.SqlConnection> eine Verbindung zu erstellen, eine Verbindungszeichenfolge anzugeben, die auf den lokalen Server zeigt, und die Verbindung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c9237-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="c9237-106">Dabei müssen Anmeldeinformationen für die Anmeldung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c9237-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="c9237-107">Die Verbindung befindet sich in einer anderen Datenbanksitzung als die gespeicherte Prozedur oder Funktion, sie kann über andere `SET`-Optionen verfügen, sie gehört zu einer separaten Transaktion, verfügt nicht über die temporären Tabellen usw.</span><span class="sxs-lookup"><span data-stu-id="c9237-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="c9237-108">Wenn der verwaltete gespeicherte Prozedur- oder Funktionscode im SQL Server-Prozess ausgeführt wird, liegt dies daran, dass eine Verbindung mit diesem Server hergestellt und eine SQL-Anweisung ausgeführt wurde, die den Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="c9237-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="c9237-109">Möglicherweise möchten Sie die gespeicherte Prozedur oder Funktion im Kontext dieser Verbindung ausführen, zusammen mit ihrer Transaktion, den `SET`-Optionen usw.</span><span class="sxs-lookup"><span data-stu-id="c9237-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="c9237-110">Dies wird als Kontextverbindung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c9237-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="c9237-111">Mit der Kontextverbindung können Sie Transact-SQL-Anweisungen in demselben Kontext ausführen, der für den Code beim ersten Aufruf galt.</span><span class="sxs-lookup"><span data-stu-id="c9237-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="c9237-112">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9237-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="c9237-113">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="c9237-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="c9237-114">Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="c9237-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="c9237-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9237-115">See Also</span></span>  
 [<span data-ttu-id="c9237-116">Erstellen von SQL Server 2005-Objekte In verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="c9237-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="c9237-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c9237-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
