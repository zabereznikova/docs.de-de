---
title: 'Vorgehensweise: Verwenden von benutzerdefinierten Skalarwertfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: da4e5e8fe4682191a0c8e2b0ce6a7b945fe63deb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781475"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="5f830-102">Vorgehensweise: Verwenden von benutzerdefinierten Skalarwertfunktionen</span><span class="sxs-lookup"><span data-stu-id="5f830-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="5f830-103">Sie können eine Clientmethode für eine Klasse einer benutzerdefinierten Funktion zuweisen. Verwenden Sie hierfür das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="5f830-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="5f830-104">Beachten Sie, dass der Hauptteil der Methode einen Ausdruck erstellt, der die Absicht des Methodenaufrufs erfasst und diesen Ausdruck zur Übersetzung und Ausführung an den <xref:System.Data.Linq.DataContext> weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="5f830-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f830-105">Die direkte Ausführung tritt nur auf, wenn die Funktion außerhalb einer Abfrage aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5f830-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="5f830-106">Weitere Informationen finden Sie unter [Vorgehensweise: Inline](how-to-call-user-defined-functions-inline.md)Aufrufe von benutzerdefinierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5f830-106">For more information, see [How to: Call User-Defined Functions Inline](how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f830-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f830-107">Example</span></span>  
 <span data-ttu-id="5f830-108">Der folgende SQL-Code zeigt eine benutzerdefinierte Skalarwertfunktion: `ReverseCustName()`.</span><span class="sxs-lookup"><span data-stu-id="5f830-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="5f830-109">Sie würden beispielsweise die folgende Clientmethode für diesen Code zuordnen:</span><span class="sxs-lookup"><span data-stu-id="5f830-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5f830-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f830-110">See also</span></span>

- [<span data-ttu-id="5f830-111">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="5f830-111">User-Defined Functions</span></span>](user-defined-functions.md)
