---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319303"
---
# <a name="spatial-functions"></a><span data-ttu-id="71853-102">Räumliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="71853-102">Spatial Functions</span></span>
<span data-ttu-id="71853-103">Es gibt kein Literalformat für räumliche Typen.</span><span class="sxs-lookup"><span data-stu-id="71853-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="71853-104">Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen.</span><span class="sxs-lookup"><span data-stu-id="71853-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="71853-105">Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:</span><span class="sxs-lookup"><span data-stu-id="71853-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="71853-106">Die <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions>-Methoden verfügen über alle räumlichen kanonischen Entity Framework-Methoden.</span><span class="sxs-lookup"><span data-stu-id="71853-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="71853-107">Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="71853-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
