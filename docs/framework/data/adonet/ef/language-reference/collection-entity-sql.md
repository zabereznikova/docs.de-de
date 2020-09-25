---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: c960ee69f8188f6dd3184b6fb31f3432f8d58fee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197949"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="f35a2-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f35a2-102">COLLECTION (Entity SQL)</span></span>

<span data-ttu-id="f35a2-103">Das COLLECTION-Schlüsselwort wird nur in der Definition einer Inlinefunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="f35a2-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="f35a2-104">Auflistungsfunktionen sind Funktionen, die sich auf eine Reihe von Werten auswirken und eine Skalarausgabe erzeugen.</span><span class="sxs-lookup"><span data-stu-id="f35a2-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f35a2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f35a2-105">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="f35a2-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f35a2-106">Arguments</span></span>  

 `type_definition`  
 <span data-ttu-id="f35a2-107">Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f35a2-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f35a2-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f35a2-108">Remarks</span></span>  

 <span data-ttu-id="f35a2-109">Weitere Informationen zum COLLECTION-Schlüsselwort finden Sie unter [Type Definitions](type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f35a2-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f35a2-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f35a2-110">Example</span></span>  

 <span data-ttu-id="f35a2-111">Im folgenden Beispiel wird veranschaulicht, wie mit dem COLLECTION-Schlüsselwort eine Auflistung von Dezimalziffern als Argument für eine Inlineabfragefunktion deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="f35a2-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="f35a2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f35a2-112">See also</span></span>

- [<span data-ttu-id="f35a2-113">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="f35a2-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
