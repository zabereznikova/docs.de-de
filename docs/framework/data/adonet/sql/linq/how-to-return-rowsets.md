---
title: "Gewusst wie: Zurückgeben von \"Rowsets\""
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
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c2a11ae83be1c7f75c5bc440c5f8162877106b07
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="e2679-102">Gewusst wie: Zurückgeben von "Rowsets"</span><span class="sxs-lookup"><span data-stu-id="e2679-102">How to: Return Rowsets</span></span>
<span data-ttu-id="e2679-103">In diesem Beispiel wird ein Rowset von der Datenbank zurückgegeben. Er enthält einen Eingabeparameter, um das Ergebnis zu filtern.</span><span class="sxs-lookup"><span data-stu-id="e2679-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="e2679-104">Wenn Sie eine gespeicherte Prozedur, die ein Rowset zurückgibt ausführen, verwenden Sie eine *Ergebnis* -Klasse, die die Rückgabe aus der gespeicherten Prozedur speichert.</span><span class="sxs-lookup"><span data-stu-id="e2679-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="e2679-105">Weitere Informationen finden Sie unter [Analysieren von LINQ to SQL-Quellcode](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="e2679-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2679-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2679-106">Example</span></span>  
 <span data-ttu-id="e2679-107">Im folgenden Beispiel wird eine gespeicherte Prozedur dargestellt, die Zeilen mit Kunden zurückgibt und anhand eines Eingabeparameters nur die Zeilen zurückgibt, die „London“ als Ort für den Kunden enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2679-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="e2679-108">Dieses Beispiel setzt eine zählbare `CustomersByCityResult`-Klasse voraus.</span><span class="sxs-lookup"><span data-stu-id="e2679-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e2679-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2679-109">See Also</span></span>  
 [<span data-ttu-id="e2679-110">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e2679-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="e2679-111">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="e2679-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
