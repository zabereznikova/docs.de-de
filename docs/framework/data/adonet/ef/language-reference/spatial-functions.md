---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7d0979b5166c847244cbeec97acf4fa4f745a259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169582"
---
# <a name="spatial-functions"></a><span data-ttu-id="5c565-102">Räumliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="5c565-102">Spatial Functions</span></span>

<span data-ttu-id="5c565-103">Es gibt kein Literalformat für räumliche Typen.</span><span class="sxs-lookup"><span data-stu-id="5c565-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="5c565-104">Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5c565-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="5c565-105">Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:</span><span class="sxs-lookup"><span data-stu-id="5c565-105">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="5c565-106">Die- <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> Methoden verfügen über alle räumlichen kanonischen Entity Framework-Methoden.</span><span class="sxs-lookup"><span data-stu-id="5c565-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="5c565-107">Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="5c565-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
