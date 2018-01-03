---
title: "Gewusst wie: Direktes Ausführen von SQL-Befehlen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a1b3b94f00e9b8fb866a81f5076fb43fe9f22951
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="51fe3-102">Gewusst wie: Direktes Ausführen von SQL-Befehlen</span><span class="sxs-lookup"><span data-stu-id="51fe3-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="51fe3-103">Bei einer <xref:System.Data.Linq.DataContext>-Verbindung können Sie <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> verwenden, um SQL-Befehle auszuführen, die keine Objekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="51fe3-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51fe3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51fe3-104">Example</span></span>  
 <span data-ttu-id="51fe3-105">Das folgende Beispiel bewirkt, dass SQL Server UnitPrice um 1.00 vergrößert.</span><span class="sxs-lookup"><span data-stu-id="51fe3-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="51fe3-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51fe3-106">See Also</span></span>  
 [<span data-ttu-id="51fe3-107">Vorgehensweise: Direktes Ausführen von SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="51fe3-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="51fe3-108">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="51fe3-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
