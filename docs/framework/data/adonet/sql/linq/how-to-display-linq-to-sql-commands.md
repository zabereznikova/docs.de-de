---
title: 'Gewusst wie: Anzeigen von LINQ to SQL-Befehlen'
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
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e53566f1311fa969dcb9c44f31664bd34b422e46
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-linq-to-sql-commands"></a><span data-ttu-id="030c4-102">Gewusst wie: Anzeigen von LINQ to SQL-Befehlen</span><span class="sxs-lookup"><span data-stu-id="030c4-102">How to: Display LINQ to SQL Commands</span></span>
<span data-ttu-id="030c4-103">Verwenden Sie <xref:System.Data.Linq.DataContext.GetCommand%2A> zur Anzeige von SQL-Befehlen und anderen Informationen.</span><span class="sxs-lookup"><span data-stu-id="030c4-103">Use <xref:System.Data.Linq.DataContext.GetCommand%2A> to display SQL commands and other information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="030c4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="030c4-104">Example</span></span>  
 <span data-ttu-id="030c4-105">Im folgenden Beispiel zeigt das Konsolenfenster die Ausgabe der Abfrage, gefolgt von den erzeugten SQL-Befehlen, den Befehlstypen und den Verbindungstypen an.</span><span class="sxs-lookup"><span data-stu-id="030c4-105">In the following example, the console window displays the output from the query, followed by the SQL commands that are generated, the type of commands, and the type of connection.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 <span data-ttu-id="030c4-106">Die Ausgabe erscheint wie folgt:</span><span class="sxs-lookup"><span data-stu-id="030c4-106">Output appears as follows:</span></span>  
  
```  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a><span data-ttu-id="030c4-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="030c4-107">See Also</span></span>  
 [<span data-ttu-id="030c4-108">Debugging-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="030c4-108">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
