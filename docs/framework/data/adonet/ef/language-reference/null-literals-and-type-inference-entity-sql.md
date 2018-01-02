---
title: "NULL-Literale und Typrückschluss (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5a8b921db06d600430fd4e10466070910119626d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="bb65c-102">NULL-Literale und Typrückschluss (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bb65c-102">Null Literals and Type Inference (Entity SQL)</span></span>
<span data-ttu-id="bb65c-103">NULL-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Typsystem kompatibel.</span><span class="sxs-lookup"><span data-stu-id="bb65c-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="bb65c-104">Für den Typ der null-Literal korrekt geschlossen werden jedoch [!INCLUDE[esql](../../../../../../includes/esql-md.md)] schränkt, in denen null-Literal verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb65c-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="bb65c-105">Typisierte Nullen</span><span class="sxs-lookup"><span data-stu-id="bb65c-105">Typed Nulls</span></span>  
 <span data-ttu-id="bb65c-106">Typisierte Nullen können stets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb65c-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="bb65c-107">Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="bb65c-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="bb65c-108">Beispielsweise kann mit dem folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukt eine NULL vom Typ Int16 erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="bb65c-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="bb65c-109">Nicht typisierte NULL-Literale</span><span class="sxs-lookup"><span data-stu-id="bb65c-109">Free-Floating Null Literals</span></span>  
 <span data-ttu-id="bb65c-110">Nicht typisierte NULL-Literale können in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="bb65c-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="bb65c-111">Als Argument eines CAST-Ausdrucks oder eines TREAT-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="bb65c-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="bb65c-112">Dies ist die empfohlene Methode zur Erstellung eines typisierten NULL-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="bb65c-112">This is the recommended way to produce a typed null expression.</span></span>  
  
-   <span data-ttu-id="bb65c-113">Als Argument einer Methode oder Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb65c-113">As an argument to a method or a function.</span></span> <span data-ttu-id="bb65c-114">Dabei gelten die Standardüberladungsregeln.</span><span class="sxs-lookup"><span data-stu-id="bb65c-114">Standard overload rules apply.</span></span>  
  
-   <span data-ttu-id="bb65c-115">Als eines der Argumente eines arithmetischen Ausdrucks wie "+", "-" oder "/".</span><span class="sxs-lookup"><span data-stu-id="bb65c-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="bb65c-116">Die anderen Argumente können keine NULL-Literale sein, da sonst kein Typrückschluss möglich ist.</span><span class="sxs-lookup"><span data-stu-id="bb65c-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
-   <span data-ttu-id="bb65c-117">Als Argumente eines logischen Ausdrucks (AND, OR oder NOT).</span><span class="sxs-lookup"><span data-stu-id="bb65c-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="bb65c-118">Von allen Argumenten ist bekannt, dass sie vom booleschen Typ sind.</span><span class="sxs-lookup"><span data-stu-id="bb65c-118">All the arguments are known to be of type Boolean.</span></span>  
  
-   <span data-ttu-id="bb65c-119">Als Argument eines IS NULL-Ausdrucks oder eines IS NOT NULL-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="bb65c-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
-   <span data-ttu-id="bb65c-120">Als ein oder mehrere Argumente eines LIKE-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="bb65c-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="bb65c-121">Von allen Argumenten wird angenommen, dass es sich um Zeichenfolgen handelt.</span><span class="sxs-lookup"><span data-stu-id="bb65c-121">All arguments are expected to be strings.</span></span>  
  
-   <span data-ttu-id="bb65c-122">Als ein oder mehrere Argumente eines Konstruktors eines benannten Typs.</span><span class="sxs-lookup"><span data-stu-id="bb65c-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
-   <span data-ttu-id="bb65c-123">Als ein oder mehrere Argumente eines Multiset-Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="bb65c-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="bb65c-124">Mindestens ein Argument des Multiset-Konstruktors muss ein Ausdruck sein, der kein NULL-Literal ist.</span><span class="sxs-lookup"><span data-stu-id="bb65c-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
-   <span data-ttu-id="bb65c-125">Als einer oder mehrere der THEN-Ausdrücke oder ELSE-Ausdrücke in einem CASE-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bb65c-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="bb65c-126">Mindestens einer der THEN-Audrücke oder ELSE-Ausdrücke im CASE-Ausdruck muss ein Ausdruck sein, der kein NULL-Literal ist.</span><span class="sxs-lookup"><span data-stu-id="bb65c-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="bb65c-127">Nicht typisierte NULL-Literale können nicht in anderen Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb65c-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="bb65c-128">Zum Beispiel können sie nicht als Argumente eines Zeilenkonstruktors verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb65c-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb65c-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb65c-129">See Also</span></span>  
 [<span data-ttu-id="bb65c-130">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bb65c-130">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
