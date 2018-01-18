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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b54bac0c9ce0b473ef8d86b039ef638b79af784f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="unsupported-functionality"></a><span data-ttu-id="5c479-102">Nicht unterstützte Funktionalität</span><span class="sxs-lookup"><span data-stu-id="5c479-102">Unsupported Functionality</span></span>
<span data-ttu-id="5c479-103">In LINQ to SQL können die folgenden SQL-Funktionen nicht durch Übersetzung von vorhandenen CLR- und .NET Framework-Konstrukten genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="5c479-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="5c479-104">Obwohl `LIKE` nicht durch direkte Übersetzung unterstützt wird, ist eine ähnliche Funktionalität in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5c479-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="5c479-105">Weitere Informationen finden Sie unter <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c479-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="5c479-106">LINQ to SQL unterstützt `DATEDIFF` nur eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="5c479-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="5c479-107">Ähnliche Funktionalität ist in der <xref:System.Data.Linq.SqlClient.SqlMethods>-Klasse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5c479-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="5c479-108">LINQ to SQL unterstützt `ROUND` nur eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="5c479-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="5c479-109">Weitere Informationen finden Sie unter ["System.Math" Methoden](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5c479-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c479-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c479-110">See Also</span></span>  
 [<span data-ttu-id="5c479-111">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="5c479-111">Data Types and Functions</span></span>](data-types-and-functions.md)
