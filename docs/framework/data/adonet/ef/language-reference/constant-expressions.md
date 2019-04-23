---
title: Konstante Ausdrücke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 10c74ede8d490bf96a9d0855889669bdc2628b01
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209202"
---
# <a name="constant-expressions"></a><span data-ttu-id="7754d-102">Konstante Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7754d-102">Constant Expressions</span></span>
<span data-ttu-id="7754d-103">Ein konstanter Ausdruck besteht aus einem konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="7754d-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="7754d-104">Konstante Werte werden sofort in konstante Befehlsstrukturausdrücke konvertiert. Es findet keine Übersetzung auf dem Client statt.</span><span class="sxs-lookup"><span data-stu-id="7754d-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="7754d-105">Dazu gehören Ausdrücke, die einen konstanten Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7754d-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="7754d-106">Daher sollte Datenquellenverhalten für alle Ausdrücke erwartet werden, die Konstanten enthalten.</span><span class="sxs-lookup"><span data-stu-id="7754d-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="7754d-107">Dies kann zu Verhalten führen, das sich von CLR-Verhalten unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="7754d-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="7754d-108">Im folgenden Beispiel wird ein konstanter Ausdruck gezeigt, der auf dem Server ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="7754d-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] <span data-ttu-id="7754d-109">unterstützt die Verwendung von Benutzerklassen als Konstanten nicht.</span><span class="sxs-lookup"><span data-stu-id="7754d-109">does not support using a user class as a constant.</span></span> <span data-ttu-id="7754d-110">Ein Eigenschaftsverweis in einer Benutzerklasse wird jedoch als konstant behandelt. Er wird in einen konstanten Ausdruck der Befehlsstruktur konvertiert und für die Datenquelle ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7754d-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7754d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7754d-111">See also</span></span>

- [<span data-ttu-id="7754d-112">Ausdrücke in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="7754d-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
