---
title: 'Vorgehensweise: Direktes Ausführen von SQL-Befehlen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 3f28351a29915bebd698e00113bb05647d8412b4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781999"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="e2583-102">Vorgehensweise: Direktes Ausführen von SQL-Befehlen</span><span class="sxs-lookup"><span data-stu-id="e2583-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="e2583-103">Bei einer <xref:System.Data.Linq.DataContext>-Verbindung können Sie <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> verwenden, um SQL-Befehle auszuführen, die keine Objekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e2583-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2583-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2583-104">Example</span></span>  
 <span data-ttu-id="e2583-105">Das folgende Beispiel bewirkt, dass SQL Server UnitPrice um 1.00 vergrößert.</span><span class="sxs-lookup"><span data-stu-id="e2583-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e2583-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2583-106">See also</span></span>

- [<span data-ttu-id="e2583-107">Vorgehensweise: Direktes Ausführen von SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e2583-107">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="e2583-108">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="e2583-108">Communicating with the Database</span></span>](communicating-with-the-database.md)
