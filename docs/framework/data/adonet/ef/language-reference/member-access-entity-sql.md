---
title: sein. (Memberzugriff) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c90c908e567ac05f344292411978ff0c80919a65
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="3fabd-103">sein.</span><span class="sxs-lookup"><span data-stu-id="3fabd-103">.</span></span> <span data-ttu-id="3fabd-104">(Memberzugriff) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3fabd-104">(Member Access) (Entity SQL)</span></span>
<span data-ttu-id="3fabd-105">Der Punktoperator (.) wird die [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Memberzugriffsoperator.</span><span class="sxs-lookup"><span data-stu-id="3fabd-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="3fabd-106">Mit dem Operator für den Memberzugriff kann auf den Wert einer Eigenschaft oder eines Felds der Instanz eines strukturellen konzeptionellen Modelltyps zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="3fabd-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fabd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fabd-107">Syntax</span></span>  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="3fabd-108">Argumente</span><span class="sxs-lookup"><span data-stu-id="3fabd-108">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3fabd-109">Eine Instanz eines strukturellen konzeptionellen Modelltyps.</span><span class="sxs-lookup"><span data-stu-id="3fabd-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="3fabd-110">Eine Eigenschaft oder ein Feld einer Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="3fabd-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fabd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fabd-111">Remarks</span></span>  
 <span data-ttu-id="3fabd-112">Mit dem Punktoperator (.) können Sie Felder eines Datensatzes extrahieren, ähnlich wie beim Extrahieren der Eigenschaften eines komplexen Typs oder Entitätstyps.</span><span class="sxs-lookup"><span data-stu-id="3fabd-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="3fabd-113">Wenn z. B. "n" vom Typ "Name" ein Member des Typs "Person" ist und "p" eine Instanz des Typs "Person" ist, ist "p.n" ein zulässiger Memberzugriffsausdruck, der einen Wert des Typs "Name" zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3fabd-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="3fabd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fabd-114">See Also</span></span>  
 [<span data-ttu-id="3fabd-115">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="3fabd-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
