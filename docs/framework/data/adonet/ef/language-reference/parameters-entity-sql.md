---
title: Parameter (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bb631a752bfe0e741b654ec6774a14c82c89157c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="e4dd5-102">Parameter (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e4dd5-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="e4dd5-103">Parameter sind Variablen, die außerhalb von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert werden, üblicherweise über eine Bindungs-API, die von einer Hostsprache verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e4dd5-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="e4dd5-104">Jeder Parameter hat einen Namen und einen Typ.</span><span class="sxs-lookup"><span data-stu-id="e4dd5-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="e4dd5-105">Parameternamen werden in Abfrageausdrücken mit einem "at" (@)-Symbol als Präfix definiert.</span><span class="sxs-lookup"><span data-stu-id="e4dd5-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="e4dd5-106">Damit sind sie von den Namen von Eigenschaften oder anderen in der Abfrage definierten Namen unterscheidbar.</span><span class="sxs-lookup"><span data-stu-id="e4dd5-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="e4dd5-107">Die Bindungs-API der Hostsprache stellt APIs für die Parameterbindung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e4dd5-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4dd5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4dd5-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4dd5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4dd5-109">See Also</span></span>  
 [<span data-ttu-id="e4dd5-110">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="e4dd5-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="e4dd5-111">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e4dd5-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
