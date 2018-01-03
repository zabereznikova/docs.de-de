---
title: "Nicht unterstützte Funktionalität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 244d9ee7accd3686729542d0f0a15966bcde7b78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="unsupported-functionality"></a><span data-ttu-id="e6257-102">Nicht unterstützte Funktionalität</span><span class="sxs-lookup"><span data-stu-id="e6257-102">Unsupported Functionality</span></span>
<span data-ttu-id="e6257-103">In LINQ to SQL können die folgenden SQL-Funktionen nicht durch Übersetzung von vorhandenen CLR- und .NET Framework-Konstrukten genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="e6257-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="e6257-104">Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e6257-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="e6257-105">Weitere Informationen finden Sie unter <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e6257-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="e6257-106">LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="e6257-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="e6257-107">Ähnliche Funktionalität ist in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e6257-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="e6257-108">LINQ to SQL unterstützt `ROUND` nur eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="e6257-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="e6257-109">Weitere Informationen finden Sie unter ["System.Math" Methoden](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e6257-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6257-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6257-110">See Also</span></span>  
 [<span data-ttu-id="e6257-111">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="e6257-111">Data Types and Functions</span></span>](data-types-and-functions.md)
