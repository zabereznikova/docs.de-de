---
title: NULL-Literale und Typrückschluss (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 5797c9f55b1a1c89cc27787af6f9ad7bfffc5767
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185066"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="278b1-102">NULL-Literale und Typrückschluss (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="278b1-102">Null Literals and Type Inference (Entity SQL)</span></span>

<span data-ttu-id="278b1-103">NULL-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Typsystem kompatibel.</span><span class="sxs-lookup"><span data-stu-id="278b1-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="278b1-104">Damit der Typ eines NULL-Literals ordnungsgemäß abgeleitet wird, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] erzwingt jedoch bestimmte Einschränkungen für die Verwendung eines NULL-Literals.</span><span class="sxs-lookup"><span data-stu-id="278b1-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="278b1-105">Typisierte Nullen</span><span class="sxs-lookup"><span data-stu-id="278b1-105">Typed Nulls</span></span>  

 <span data-ttu-id="278b1-106">Typisierte Nullen können stets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="278b1-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="278b1-107">Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="278b1-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="278b1-108">Beispielsweise kann mit dem folgenden -Konstrukt eine NULL vom Typ Int16 erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="278b1-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="278b1-109">Nicht typisierte NULL-Literale</span><span class="sxs-lookup"><span data-stu-id="278b1-109">Free-Floating Null Literals</span></span>  

 <span data-ttu-id="278b1-110">Nicht typisierte NULL-Literale können in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="278b1-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
- <span data-ttu-id="278b1-111">Als Argument eines CAST-Ausdrucks oder eines TREAT-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="278b1-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="278b1-112">Dies ist die empfohlene Methode zur Erstellung eines typisierten NULL-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="278b1-112">This is the recommended way to produce a typed null expression.</span></span>  
  
- <span data-ttu-id="278b1-113">Als Argument einer Methode oder Funktion.</span><span class="sxs-lookup"><span data-stu-id="278b1-113">As an argument to a method or a function.</span></span> <span data-ttu-id="278b1-114">Dabei gelten die Standardüberladungsregeln.</span><span class="sxs-lookup"><span data-stu-id="278b1-114">Standard overload rules apply.</span></span>  
  
- <span data-ttu-id="278b1-115">Als eines der Argumente eines arithmetischen Ausdrucks wie "+", "-" oder "/".</span><span class="sxs-lookup"><span data-stu-id="278b1-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="278b1-116">Die anderen Argumente können keine NULL-Literale sein, da sonst kein Typrückschluss möglich ist.</span><span class="sxs-lookup"><span data-stu-id="278b1-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
- <span data-ttu-id="278b1-117">Als Argumente eines logischen Ausdrucks (AND, OR oder NOT).</span><span class="sxs-lookup"><span data-stu-id="278b1-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="278b1-118">Von allen Argumenten ist bekannt, dass sie vom booleschen Typ sind.</span><span class="sxs-lookup"><span data-stu-id="278b1-118">All the arguments are known to be of type Boolean.</span></span>  
  
- <span data-ttu-id="278b1-119">Als Argument eines IS NULL-Ausdrucks oder eines IS NOT NULL-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="278b1-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
- <span data-ttu-id="278b1-120">Als ein oder mehrere Argumente eines LIKE-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="278b1-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="278b1-121">Von allen Argumenten wird angenommen, dass es sich um Zeichenfolgen handelt.</span><span class="sxs-lookup"><span data-stu-id="278b1-121">All arguments are expected to be strings.</span></span>  
  
- <span data-ttu-id="278b1-122">Als ein oder mehrere Argumente eines Konstruktors eines benannten Typs.</span><span class="sxs-lookup"><span data-stu-id="278b1-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
- <span data-ttu-id="278b1-123">Als ein oder mehrere Argumente eines Multiset-Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="278b1-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="278b1-124">Mindestens ein Argument des Multiset-Konstruktors muss ein Ausdruck sein, der kein NULL-Literal ist.</span><span class="sxs-lookup"><span data-stu-id="278b1-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
- <span data-ttu-id="278b1-125">Als einer oder mehrere der THEN-Ausdrücke oder ELSE-Ausdrücke in einem CASE-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="278b1-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="278b1-126">Mindestens einer der THEN-Audrücke oder ELSE-Ausdrücke im CASE-Ausdruck muss ein Ausdruck sein, der kein NULL-Literal ist.</span><span class="sxs-lookup"><span data-stu-id="278b1-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="278b1-127">Nicht typisierte NULL-Literale können nicht in anderen Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="278b1-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="278b1-128">Zum Beispiel können sie nicht als Argumente eines Zeilenkonstruktors verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="278b1-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278b1-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="278b1-129">See also</span></span>

- [<span data-ttu-id="278b1-130">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="278b1-130">Entity SQL Overview</span></span>](entity-sql-overview.md)
