---
title: System.Math-Methoden
ms.date: 03/30/2017
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
ms.openlocfilehash: 1dae31b30962505c07c198f3bd35fceb8f400efb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917682"
---
# <a name="systemmath-methods"></a>System.Math-Methoden
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden <xref:System.Math>-Methoden nicht.  
  
- <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
- <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a>Unterschiede zu .NET  
 .NET Framework weist gegenüber SQL Server eine andere Rundungssemantik auf. Die <xref:System.Math.Round%2A> -Methode in der .NET Framework führt *Banker rounding*, bei dem Runden von Zahlen, die auf, 5 enden auf die nächste ungerade Ziffer statt auf die nächsthöhere Ziffer gerundet. 2,5 wird zu 2 abgerundet, während 3,5 zu 4 aufgerundet wird. (Mit dieser Technik können bei großen Datentransaktionen systematische Abweichungen gegenüber höheren Werten vermieden werden.)  
  
 In SQL rundet die `ROUND`-Funktion stattdessen immer weg von 0. 2,5 wird daher auf 3 gerundet (im Gegensatz zur Rundung auf 2 in .NET Framework).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leitet an die SQL-`ROUND`-Semantik weiter und versucht nicht, eine unverzerrte Rundung (Banker's Rounding) zu implementieren.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
