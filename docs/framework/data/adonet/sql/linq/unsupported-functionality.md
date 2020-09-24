---
title: Nicht unterstützte Funktionalität
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164154"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="87fc0-102">Nicht unterstützte Funktionalität</span><span class="sxs-lookup"><span data-stu-id="87fc0-102">Unsupported Functionality</span></span>

<span data-ttu-id="87fc0-103">In LINQ to SQL können die folgenden SQL-Funktionen nicht durch Übersetzung von vorhandenen CLR- und .NET Framework-Konstrukten genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="87fc0-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="87fc0-104">Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="87fc0-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="87fc0-105">Weitere Informationen finden Sie unter <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87fc0-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="87fc0-106">LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="87fc0-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="87fc0-107">Ähnliche Funktionalität ist in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="87fc0-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="87fc0-108">LINQ to SQL unterstützt `ROUND` nur eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="87fc0-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="87fc0-109">Weitere Informationen finden Sie unter [System. Math-Methoden](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="87fc0-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87fc0-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87fc0-110">See also</span></span>

- [<span data-ttu-id="87fc0-111">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="87fc0-111">Data Types and Functions</span></span>](data-types-and-functions.md)
