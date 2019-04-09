---
title: 'Vorgehensweise: Direktes Ausführen von SQL-Befehlen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: eeac6272f176ac8e780b72b0076d032ad9e8f108
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078901"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="36a50-102">Vorgehensweise: Direktes Ausführen von SQL-Befehlen</span><span class="sxs-lookup"><span data-stu-id="36a50-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="36a50-103">Bei einer <xref:System.Data.Linq.DataContext>-Verbindung können Sie <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> verwenden, um SQL-Befehle auszuführen, die keine Objekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="36a50-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36a50-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36a50-104">Example</span></span>  
 <span data-ttu-id="36a50-105">Das folgende Beispiel bewirkt, dass SQL Server UnitPrice um 1.00 vergrößert.</span><span class="sxs-lookup"><span data-stu-id="36a50-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="36a50-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36a50-106">See also</span></span>

- [<span data-ttu-id="36a50-107">Vorgehensweise: Direktes Ausführen von SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="36a50-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="36a50-108">Kommunizieren mit der Datenbank</span><span class="sxs-lookup"><span data-stu-id="36a50-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
