---
title: System.Math-Methoden
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: e91c8ea95d21288ad2577f1550333febd448766d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158200"
---
# <a name="systemmath-methods"></a><span data-ttu-id="1557f-102">System.Math-Methoden</span><span class="sxs-lookup"><span data-stu-id="1557f-102">System.Math Methods</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="1557f-103">unterstützt die folgenden <xref:System.Math>-Methoden nicht.</span><span class="sxs-lookup"><span data-stu-id="1557f-103">does not support the following <xref:System.Math> methods.</span></span>  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="1557f-104">Unterschiede zu .NET</span><span class="sxs-lookup"><span data-stu-id="1557f-104">Differences from .NET</span></span>  

 <span data-ttu-id="1557f-105">.NET Framework weist gegenüber SQL Server eine andere Rundungssemantik auf.</span><span class="sxs-lookup"><span data-stu-id="1557f-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="1557f-106">Die <xref:System.Math.Round%2A> -Methode im-.NET Framework führt die *Rundung des Bankers*aus, bei der Zahlen, die in 0,5 enden, auf die nächste gerade Ziffer und nicht auf die nächste höhere Ziffer gerundet werden.</span><span class="sxs-lookup"><span data-stu-id="1557f-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="1557f-107">2,5 wird zu 2 abgerundet, während 3,5 zu 4 aufgerundet wird.</span><span class="sxs-lookup"><span data-stu-id="1557f-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="1557f-108">(Mit dieser Technik können bei großen Datentransaktionen systematische Abweichungen gegenüber höheren Werten vermieden werden.)</span><span class="sxs-lookup"><span data-stu-id="1557f-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="1557f-109">In SQL rundet die `ROUND`-Funktion stattdessen immer weg von 0.</span><span class="sxs-lookup"><span data-stu-id="1557f-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="1557f-110">2,5 wird daher auf 3 gerundet (im Gegensatz zur Rundung auf 2 in .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="1557f-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="1557f-111">leitet an die SQL-`ROUND`-Semantik weiter und versucht nicht, eine unverzerrte Rundung (Banker's Rounding) zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="1557f-111">passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1557f-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1557f-112">See also</span></span>

- [<span data-ttu-id="1557f-113">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="1557f-113">Data Types and Functions</span></span>](data-types-and-functions.md)
