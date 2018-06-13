---
title: Räumliche Funktionen
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7b78cbf4dc53ba1bc4148fa0077615e43cc8f9f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763929"
---
# <a name="spatial-functions"></a><span data-ttu-id="cfa32-102">Räumliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="cfa32-102">Spatial Functions</span></span>
<span data-ttu-id="cfa32-103">Es gibt kein Literalformat für räumliche Typen.</span><span class="sxs-lookup"><span data-stu-id="cfa32-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="cfa32-104">Sie können jedoch kanonische Entity Framework-Funktionen verwenden, die Sie mit Zeichenfolgen im WKT (Well-Known Text)-Format aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cfa32-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="cfa32-105">Beispielsweise wird durch den folgenden Funktionsaufruf ein Geometriepunkt erstellt:</span><span class="sxs-lookup"><span data-stu-id="cfa32-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="cfa32-106">Die [SpatialEdmFunctions-Methoden](http://msdn.microsoft.com/library/hh749531.aspx) Seite listet aller räumliche kanonische Entity Framework-Methoden.</span><span class="sxs-lookup"><span data-stu-id="cfa32-106">The [SpatialEdmFunctions Methods](http://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="cfa32-107">Klicken Sie auf die gewünschte Methode, um herauszufinden, welche Parameter an eine Funktion übergeben werden sollten.</span><span class="sxs-lookup"><span data-stu-id="cfa32-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
