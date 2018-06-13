---
title: 'Gewusst wie: Zurückgeben von "Rowsets"'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: a2666b752d936e10d377113d5bf18111393df3ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361136"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="88272-102">Gewusst wie: Zurückgeben von "Rowsets"</span><span class="sxs-lookup"><span data-stu-id="88272-102">How to: Return Rowsets</span></span>
<span data-ttu-id="88272-103">In diesem Beispiel wird ein Rowset von der Datenbank zurückgegeben. Er enthält einen Eingabeparameter, um das Ergebnis zu filtern.</span><span class="sxs-lookup"><span data-stu-id="88272-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="88272-104">Wenn Sie eine gespeicherte Prozedur, die ein Rowset zurückgibt ausführen, verwenden Sie eine *Ergebnis* -Klasse, die die Rückgabe aus der gespeicherten Prozedur speichert.</span><span class="sxs-lookup"><span data-stu-id="88272-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="88272-105">Weitere Informationen finden Sie unter [Analysieren von LINQ to SQL-Quellcode](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="88272-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88272-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88272-106">Example</span></span>  
 <span data-ttu-id="88272-107">Im folgenden Beispiel wird eine gespeicherte Prozedur dargestellt, die Zeilen mit Kunden zurückgibt und anhand eines Eingabeparameters nur die Zeilen zurückgibt, die „London“ als Ort für den Kunden enthalten.</span><span class="sxs-lookup"><span data-stu-id="88272-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="88272-108">Dieses Beispiel setzt eine zählbare `CustomersByCityResult`-Klasse voraus.</span><span class="sxs-lookup"><span data-stu-id="88272-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88272-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88272-109">See Also</span></span>  
 [<span data-ttu-id="88272-110">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="88272-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="88272-111">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="88272-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
