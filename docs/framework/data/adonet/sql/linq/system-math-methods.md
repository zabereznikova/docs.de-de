---
title: System.Math-Methoden
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 1dae31b30962505c07c198f3bd35fceb8f400efb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141712"
---
# <a name="systemmath-methods"></a><span data-ttu-id="4077c-102">System.Math-Methoden</span><span class="sxs-lookup"><span data-stu-id="4077c-102">System.Math Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4077c-103">unterstützt die folgenden <xref:System.Math>-Methoden nicht.</span><span class="sxs-lookup"><span data-stu-id="4077c-103">does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="4077c-104">Unterschiede zu .NET</span><span class="sxs-lookup"><span data-stu-id="4077c-104">Differences from .NET</span></span>  
 <span data-ttu-id="4077c-105">.NET Framework weist gegenüber SQL Server eine andere Rundungssemantik auf.</span><span class="sxs-lookup"><span data-stu-id="4077c-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="4077c-106">Die <xref:System.Math.Round%2A> -Methode in der .NET Framework führt *Banker rounding*, bei dem Runden von Zahlen, die auf, 5 enden auf die nächste ungerade Ziffer statt auf die nächsthöhere Ziffer gerundet.</span><span class="sxs-lookup"><span data-stu-id="4077c-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="4077c-107">2,5 wird zu 2 abgerundet, während 3,5 zu 4 aufgerundet wird.</span><span class="sxs-lookup"><span data-stu-id="4077c-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="4077c-108">(Mit dieser Technik können bei großen Datentransaktionen systematische Abweichungen gegenüber höheren Werten vermieden werden.)</span><span class="sxs-lookup"><span data-stu-id="4077c-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="4077c-109">In SQL rundet die `ROUND`-Funktion stattdessen immer weg von 0.</span><span class="sxs-lookup"><span data-stu-id="4077c-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="4077c-110">2,5 wird daher auf 3 gerundet (im Gegensatz zur Rundung auf 2 in .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="4077c-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4077c-111">leitet an die SQL-`ROUND`-Semantik weiter und versucht nicht, eine unverzerrte Rundung (Banker's Rounding) zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4077c-111">passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4077c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4077c-112">See also</span></span>

- [<span data-ttu-id="4077c-113">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="4077c-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
