---
title: 'Vorgehensweise: Verwenden von benutzerdefinierten Tabellenwertfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: c4b5290e4f1aa69c7f55951d526ccb303a5a95ec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003182"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="c0f65-102">Vorgehensweise: Verwenden von benutzerdefinierten Tabellenwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="c0f65-102">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="c0f65-103">Eine Tabellenwertfunktion gibt ein einzelnes Rowset (im Gegensatz zu gespeicherten Prozeduren, die mehrere Ergebnisformen zurückgeben können) zurück.</span><span class="sxs-lookup"><span data-stu-id="c0f65-103">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="c0f65-104">Da der Rückgabetyp einer Tabellenwertfunktion `Table` lautet, können Sie eine Tabellenwertfunktion überall dort in SQL nutzen, wo Sie eine Tabelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c0f65-104">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="c0f65-105">Außerdem können Sie die Tabellenwertfunktion so wie eine Tabelle behandeln.</span><span class="sxs-lookup"><span data-stu-id="c0f65-105">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f65-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0f65-106">Example</span></span>  
 <span data-ttu-id="c0f65-107">Die folgende SQL-Funktion legt explizit fest, dass sie eine `TABLE` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c0f65-107">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="c0f65-108">Deshalb wird die zurückgegebene Rowsetstruktur implizit definiert.</span><span class="sxs-lookup"><span data-stu-id="c0f65-108">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```sql
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="c0f65-109">ordnet die Funktion wie folgt zu:</span><span class="sxs-lookup"><span data-stu-id="c0f65-109">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="c0f65-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0f65-110">Example</span></span>  
 <span data-ttu-id="c0f65-111">Der folgende SQL-Code zeigt, dass Sie einen Join zu der von der Funktion zurückgegebenen Tabelle herstellen können. Andernfalls erfolgt die Behandlung wie bei jeder anderen Tabelle:</span><span class="sxs-lookup"><span data-stu-id="c0f65-111">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```sql
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="c0f65-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] würde die Abfrage wie folgt gerendert werden:</span><span class="sxs-lookup"><span data-stu-id="c0f65-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c0f65-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0f65-113">See also</span></span>

- [<span data-ttu-id="c0f65-114">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="c0f65-114">User-Defined Functions</span></span>](user-defined-functions.md)
