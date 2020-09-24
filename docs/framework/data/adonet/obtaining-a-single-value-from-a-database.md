---
title: Abrufen eines einzelnen Werts aus einer Datenbank
description: Erfahren Sie, wie Sie einen einzelnen Wert in ADO.net zurückgeben. Dieser Beispielcode gibt den Identitäts Spaltenwert für einen eingefügten Datensatz zurück.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 9ce29bc1321814bd60cfaacd222fc55a3fbf12ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150725"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="6ffd6-104">Abrufen eines einzelnen Werts aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="6ffd6-104">Obtaining a Single Value from a Database</span></span>

<span data-ttu-id="6ffd6-105">Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="6ffd6-106">Beispielsweise können Sie das Ergebnis einer Aggregatfunktion wie count ( \* ), Sum (Price) oder AVG (Menge) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="6ffd6-107">Das **Command** -Objekt bietet die Möglichkeit, einzelne Werte mithilfe der **ExecuteScalar** -Methode zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="6ffd6-108">Die **ExecuteScalar** -Methode gibt den Wert der ersten Spalte der ersten Zeile des Resultsets als Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="6ffd6-109">Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="6ffd6-110">Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6ffd6-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ffd6-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ffd6-111">See also</span></span>

- [<span data-ttu-id="6ffd6-112">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="6ffd6-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="6ffd6-113">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="6ffd6-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="6ffd6-114">"DbConnection", "DbCommand" und "DbException"</span><span class="sxs-lookup"><span data-stu-id="6ffd6-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="6ffd6-115">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ffd6-115">ADO.NET Overview</span></span>](ado-net-overview.md)
