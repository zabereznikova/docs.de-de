---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: ad6b722e84aae40354e30434b107752d02352645
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776938"
---
# <a name="spatial-functions"></a><span data-ttu-id="c9867-102">Räumliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="c9867-102">Spatial Functions</span></span>
<span data-ttu-id="c9867-103">Es gibt kein Literalformat für räumliche Typen.</span><span class="sxs-lookup"><span data-stu-id="c9867-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="c9867-104">Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c9867-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="c9867-105">Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:</span><span class="sxs-lookup"><span data-stu-id="c9867-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="c9867-106">Die [SpatialEdmFunctions-Methoden](https://msdn.microsoft.com/library/hh749531.aspx) Seite listet aller räumliche kanonische Entity Framework-Methoden.</span><span class="sxs-lookup"><span data-stu-id="c9867-106">The [SpatialEdmFunctions Methods](https://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="c9867-107">Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="c9867-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
