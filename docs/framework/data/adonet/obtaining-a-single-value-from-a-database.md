---
title: Abrufen eines einzelnen Werts aus einer Datenbank
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: e362a71f902739663961099cf2f43dff90b4743c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711459"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="6eda7-102">Abrufen eines einzelnen Werts aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="6eda7-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="6eda7-103">Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="6eda7-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="6eda7-104">Sie möchten z. B. das Ergebnis einer Aggregatfunktion wie z. B. Anzahl zurückgeben (\*), SUM(Price) oder AVG(Quantity).</span><span class="sxs-lookup"><span data-stu-id="6eda7-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="6eda7-105">Die **Befehl** Objekt bietet die Möglichkeit zum Zurückgeben von einzelner Werten, die mit der **"ExecuteScalar"** Methode.</span><span class="sxs-lookup"><span data-stu-id="6eda7-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="6eda7-106">Die **"ExecuteScalar"** Methode wird als Skalarwert, der Wert der ersten Spalte der ersten Zeile des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="6eda7-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="6eda7-107">Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="6eda7-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="6eda7-108">Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6eda7-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6eda7-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eda7-109">See also</span></span>
- [<span data-ttu-id="6eda7-110">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="6eda7-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="6eda7-111">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="6eda7-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)
- [<span data-ttu-id="6eda7-112">DbConnection, DbCommand und DbException</span><span class="sxs-lookup"><span data-stu-id="6eda7-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="6eda7-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="6eda7-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
