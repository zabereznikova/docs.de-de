---
title: System.Math-Methoden
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: af5e18b9c4334cfab26c9a84ac647bb433391ef1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="systemmath-methods"></a><span data-ttu-id="d3505-102">System.Math-Methoden</span><span class="sxs-lookup"><span data-stu-id="d3505-102">System.Math Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d3505-103"> unterstützt die folgenden <xref:System.Math>-Methoden nicht.</span><span class="sxs-lookup"><span data-stu-id="d3505-103"> does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="d3505-104">Unterschiede zu .NET</span><span class="sxs-lookup"><span data-stu-id="d3505-104">Differences from .NET</span></span>  
 <span data-ttu-id="d3505-105">.NET Framework weist gegenüber SQL Server eine andere Rundungssemantik auf.</span><span class="sxs-lookup"><span data-stu-id="d3505-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="d3505-106">Die <xref:System.Math.Round%2A> -Methode in .NET Framework führt *Banker rounding*, bei dem Runden von Zahlen, die auf, 5 enden auf die nächsthöhere Ziffer, statt auf die nächste ungerade Ziffer.</span><span class="sxs-lookup"><span data-stu-id="d3505-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="d3505-107">2,5 wird zu 2 abgerundet, während 3,5 zu 4 aufgerundet wird.</span><span class="sxs-lookup"><span data-stu-id="d3505-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="d3505-108">(Mit dieser Technik können bei großen Datentransaktionen systematische Abweichungen gegenüber höheren Werten vermieden werden.)</span><span class="sxs-lookup"><span data-stu-id="d3505-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="d3505-109">In SQL rundet die `ROUND`-Funktion stattdessen immer weg von 0.</span><span class="sxs-lookup"><span data-stu-id="d3505-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="d3505-110">2,5 wird daher auf 3 gerundet (im Gegensatz zur Rundung auf 2 in .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="d3505-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d3505-111"> leitet an die SQL-`ROUND`-Semantik weiter und versucht nicht, eine unverzerrte Rundung (Banker's Rounding) zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="d3505-111"> passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3505-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3505-112">See Also</span></span>  
 [<span data-ttu-id="d3505-113">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3505-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
