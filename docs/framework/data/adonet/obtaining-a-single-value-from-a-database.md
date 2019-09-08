---
title: Abrufen eines einzelnen Werts aus einer Datenbank
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: fb43d21546a0e98e87aab23db9213309b62320b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794749"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="63d3f-102">Abrufen eines einzelnen Werts aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="63d3f-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="63d3f-103">Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="63d3f-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="63d3f-104">Beispielsweise können Sie das Ergebnis einer Aggregatfunktion wie count (\*), Sum (Price) oder AVG (Menge) zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="63d3f-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="63d3f-105">Das **Command** -Objekt bietet die Möglichkeit, einzelne Werte mithilfe der **ExecuteScalar** -Methode zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="63d3f-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="63d3f-106">Die **ExecuteScalar** -Methode gibt den Wert der ersten Spalte der ersten Zeile des Resultsets als Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="63d3f-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="63d3f-107">Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="63d3f-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="63d3f-108">Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63d3f-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="63d3f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63d3f-109">See also</span></span>

- [<span data-ttu-id="63d3f-110">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="63d3f-110">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="63d3f-111">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="63d3f-111">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="63d3f-112">DbConnection, DbCommand und DbException</span><span class="sxs-lookup"><span data-stu-id="63d3f-112">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="63d3f-113">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="63d3f-113">ADO.NET Overview</span></span>](ado-net-overview.md)
