---
title: NULL-Literale und Typrückschluss (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 22b548f2fc889b20f76a41001438f75c25f99c00
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118091"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="a9ce3-102">NULL-Literale und Typrückschluss (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a9ce3-102">Null Literals and Type Inference (Entity SQL)</span></span>
<span data-ttu-id="a9ce3-103">NULL-Literale sind mit allen Typen im [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Typsystem kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="a9ce3-104">Für den Typ der null-Literal korrekt geschlossen werden jedoch [!INCLUDE[esql](../../../../../../includes/esql-md.md)] gelten bestimmte Einschränkungen auf, in dem ein null-Literal verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="a9ce3-105">Typisierte Nullen</span><span class="sxs-lookup"><span data-stu-id="a9ce3-105">Typed Nulls</span></span>  
 <span data-ttu-id="a9ce3-106">Typisierte Nullen können stets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="a9ce3-107">Typrückschluss ist für typisierte Nullen nicht erforderlich, da der Typ bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="a9ce3-108">Beispielsweise kann mit dem folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Konstrukt eine NULL vom Typ Int16 erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="a9ce3-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="a9ce3-109">Nicht typisierte NULL-Literale</span><span class="sxs-lookup"><span data-stu-id="a9ce3-109">Free-Floating Null Literals</span></span>  
 <span data-ttu-id="a9ce3-110">Nicht typisierte NULL-Literale können in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a9ce3-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="a9ce3-111">Als Argument eines CAST-Ausdrucks oder eines TREAT-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="a9ce3-112">Dies ist die empfohlene Methode zur Erstellung eines typisierten NULL-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-112">This is the recommended way to produce a typed null expression.</span></span>  
  
-   <span data-ttu-id="a9ce3-113">Als Argument einer Methode oder Funktion.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-113">As an argument to a method or a function.</span></span> <span data-ttu-id="a9ce3-114">Dabei gelten die Standardüberladungsregeln.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-114">Standard overload rules apply.</span></span>  
  
-   <span data-ttu-id="a9ce3-115">Als eines der Argumente eines arithmetischen Ausdrucks wie "+", "-" oder "/".</span><span class="sxs-lookup"><span data-stu-id="a9ce3-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="a9ce3-116">Die anderen Argumente können keine NULL-Literale sein, da sonst kein Typrückschluss möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
-   <span data-ttu-id="a9ce3-117">Als Argumente eines logischen Ausdrucks (AND, OR oder NOT).</span><span class="sxs-lookup"><span data-stu-id="a9ce3-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="a9ce3-118">Von allen Argumenten ist bekannt, dass sie vom booleschen Typ sind.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-118">All the arguments are known to be of type Boolean.</span></span>  
  
-   <span data-ttu-id="a9ce3-119">Als Argument eines IS NULL-Ausdrucks oder eines IS NOT NULL-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
-   <span data-ttu-id="a9ce3-120">Als ein oder mehrere Argumente eines LIKE-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="a9ce3-121">Von allen Argumenten wird angenommen, dass es sich um Zeichenfolgen handelt.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-121">All arguments are expected to be strings.</span></span>  
  
-   <span data-ttu-id="a9ce3-122">Als ein oder mehrere Argumente eines Konstruktors eines benannten Typs.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
-   <span data-ttu-id="a9ce3-123">Als ein oder mehrere Argumente eines Multiset-Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="a9ce3-124">Mindestens ein Argument des Multiset-Konstruktors muss ein Ausdruck sein, der kein NULL-Literal ist.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
-   <span data-ttu-id="a9ce3-125">Als einer oder mehrere der THEN-Ausdrücke oder ELSE-Ausdrücke in einem CASE-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="a9ce3-126">Mindestens einer der THEN-Audrücke oder ELSE-Ausdrücke im CASE-Ausdruck muss ein Ausdruck sein, der kein NULL-Literal ist.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="a9ce3-127">Nicht typisierte NULL-Literale können nicht in anderen Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="a9ce3-128">Zum Beispiel können sie nicht als Argumente eines Zeilenkonstruktors verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ce3-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9ce3-129">See also</span></span>

- [<span data-ttu-id="a9ce3-130">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a9ce3-130">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
