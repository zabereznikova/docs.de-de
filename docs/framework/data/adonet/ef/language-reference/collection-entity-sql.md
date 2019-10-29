---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039911"
---
# <a name="collection-entity-sql"></a><span data-ttu-id="9c297-102">COLLECTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9c297-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="9c297-103">Das COLLECTION-Schlüsselwort wird nur in der Definition einer Inlinefunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="9c297-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="9c297-104">Auflistungsfunktionen sind Funktionen, die sich auf eine Reihe von Werten auswirken und eine Skalarausgabe erzeugen.</span><span class="sxs-lookup"><span data-stu-id="9c297-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c297-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c297-105">Syntax</span></span>  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a><span data-ttu-id="9c297-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="9c297-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="9c297-107">Ein Ausdruck, der eine Auflistung von unterstützten Typen, Zeilen oder Verweisen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9c297-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c297-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c297-108">Remarks</span></span>  
 <span data-ttu-id="9c297-109">Weitere Informationen zum COLLECTION-Schlüsselwort finden Sie unter [Type Definitions](type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9c297-109">For more information about the COLLECTION keyword, see [Type Definitions](type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c297-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c297-110">Example</span></span>  
 <span data-ttu-id="9c297-111">Im folgenden Beispiel wird veranschaulicht, wie mit dem COLLECTION-Schlüsselwort eine Auflistung von Dezimalziffern als Argument für eine Inlineabfragefunktion deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="9c297-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="9c297-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c297-112">See also</span></span>

- [<span data-ttu-id="9c297-113">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="9c297-113">Entity SQL Reference</span></span>](entity-sql-reference.md)
