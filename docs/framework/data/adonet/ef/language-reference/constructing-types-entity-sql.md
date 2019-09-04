---
title: Konstruktionstypen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: 7113aaf1c2caa982a8ab4751928856c1271570cb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251122"
---
# <a name="constructing-types-entity-sql"></a><span data-ttu-id="09432-102">Konstruktionstypen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="09432-102">Constructing Types (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="09432-103">stellt drei Arten von Konstruktoren bereit: Zeilenkonstruktoren, Konstruktoren benannter Typen und Auflistungskonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="09432-103">provides three kinds of constructors: row constructors, named type constructors, and collection constructors.</span></span>  
  
## <a name="row-constructors"></a><span data-ttu-id="09432-104">Zeilenkonstruktoren</span><span class="sxs-lookup"><span data-stu-id="09432-104">Row Constructors</span></span>  
 <span data-ttu-id="09432-105">Zeilenkonstruktoren werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zur Erstellung anonymer, strukturell typisierter Datensätze aus einem oder mehreren Werten verwendet.</span><span class="sxs-lookup"><span data-stu-id="09432-105">You use row constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="09432-106">Beim Ergebnistyp eines Zeilenkonstruktors handelt es sich um einen Zeilentyp, dessen Feldtypen den Typen der zur Erstellung der Zeile verwendeten Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="09432-106">The result type of a row constructor is a row type whose field types correspond to the types of the values used to construct the row.</span></span> <span data-ttu-id="09432-107">Mit dem folgenden Ausdruck wird beispielsweise ein Wert vom Typ `Record(a int, b string, c int)`erstellt:</span><span class="sxs-lookup"><span data-stu-id="09432-107">For example, the following expression constructs a value of type `Record(a int, b string, c int)`:</span></span>  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 <span data-ttu-id="09432-108">Wenn für einen Ausdruck in einem Zeilenkonstruktor kein Alias angegeben ist, wird vom Entity Framework ein Alias generiert.</span><span class="sxs-lookup"><span data-stu-id="09432-108">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="09432-109">Weitere Informationen finden Sie im Abschnitt "Aliasing-Regeln" unter [Bezeichner.](identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="09432-109">For more information, see the "Aliasing Rules" section in [Identifiers](identifiers-entity-sql.md).</span></span>  
  
 <span data-ttu-id="09432-110">Die folgenden Regeln gelten für Ausdrucksaliasing in einem Zeilenkonstruktor:</span><span class="sxs-lookup"><span data-stu-id="09432-110">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="09432-111">Ausdrücke in einem Zeilenkonstruktor können nicht auf andere Aliase im gleichen Konstruktor verweisen.</span><span class="sxs-lookup"><span data-stu-id="09432-111">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="09432-112">Zwei Ausdrücke im gleichen Zeilenkonstruktor können nicht über den gleichen Alias verfügen.</span><span class="sxs-lookup"><span data-stu-id="09432-112">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="09432-113">Weitere Informationen zu Zeilenkonstruktoren finden Sie unter [Row](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="09432-113">For more information about row constructors, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="collection-constructors"></a><span data-ttu-id="09432-114">Auflistungskonstruktoren</span><span class="sxs-lookup"><span data-stu-id="09432-114">Collection Constructors</span></span>  
 <span data-ttu-id="09432-115">Mithilfe von Auflistungskonstruktoren wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] aus einer Liste mit Werten eine Instanz eines Multisets erstellt.</span><span class="sxs-lookup"><span data-stu-id="09432-115">You use collection constructors in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="09432-116">Alle Werte im Konstruktor müssen vom beiderseitig kompatiblen Typ `T` sein, und der Konstruktor erstellt eine Auflistung des Typs `Multiset<T>`.</span><span class="sxs-lookup"><span data-stu-id="09432-116">All the values in the constructor must be of mutually compatible type `T`, and the constructor produces a collection of type `Multiset<T>`.</span></span> <span data-ttu-id="09432-117">Zum Beispiel erstellt der folgende Ausdruck eine Auflistung von ganzen Zahlen:</span><span class="sxs-lookup"><span data-stu-id="09432-117">For example, the following expression creates a collection of integers:</span></span>  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 <span data-ttu-id="09432-118">Leere Multiset-Konstruktoren sind nicht zugelassen, da der Typ der Elemente nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="09432-118">Empty multiset constructors are not allowed because the type of the elements cannot be determined.</span></span> <span data-ttu-id="09432-119">Der folgende Ausdruck ist ungültig:</span><span class="sxs-lookup"><span data-stu-id="09432-119">The following is not valid:</span></span>  
  
 `multiset() {}`  
  
 <span data-ttu-id="09432-120">Weitere Informationen finden Sie unter [Multiset](multiset-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="09432-120">For more information, see [MULTISET](multiset-entity-sql.md).</span></span>  
  
## <a name="named-type-constructors-namedtype-initializers"></a><span data-ttu-id="09432-121">Konstruktoren benannter Typen (NamedType-Initialisierer)</span><span class="sxs-lookup"><span data-stu-id="09432-121">Named Type Constructors (NamedType Initializers)</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="09432-122">ermöglicht Typenkonstruktoren (Initialisierern) das Erstellen von Instanzen benannter komplexer Typen und Entitätstypen.</span><span class="sxs-lookup"><span data-stu-id="09432-122">allows type constructors (initializers) to create instances of named complex types and entity types.</span></span> <span data-ttu-id="09432-123">Der folgende Ausdruck erstellt z. B. eine Instanz eines `Person`-Typs.</span><span class="sxs-lookup"><span data-stu-id="09432-123">For example, the following expression creates an instance of a `Person` type.</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="09432-124">Mit dem folgenden Ausdruck wird eine Instanz eines komplexen Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="09432-124">The following expression creates an instance of a complex type.</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="09432-125">Mit dem folgenden Ausdruck wird eine Instanz eines geschachtelten komplexen Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="09432-125">The following expression creates an instance of a nested complex type.</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="09432-126">Mit dem folgenden Ausdruck wird eine Instanz einer Entität mit einem geschachtelten komplexen Typ erstellt.</span><span class="sxs-lookup"><span data-stu-id="09432-126">The following expression creates an instance of an entity with a nested complex type.</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="09432-127">Im folgenden Beispiel wird gezeigt, wie eine Eigenschaft eines komplexen Typs mit NULL initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="09432-127">The following example shows how to initialize a property of a complex type to null.</span></span> `MyModel.ZipCode(‘98118’, null)`  
  
 <span data-ttu-id="09432-128">Die Reihenfolge der Argumente des Konstruktors sollten mit der Reihenfolge der Deklaration der Attribute des Typs übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="09432-128">The arguments to the constructor are assumed to be in the same order as the declaration of the attributes of the type.</span></span>  
  
 <span data-ttu-id="09432-129">Weitere Informationen finden Sie unter [Konstruktor für benannte Typen](named-type-constructor-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="09432-129">For more information, see [Named Type Constructor](named-type-constructor-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09432-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09432-130">See also</span></span>

- [<span data-ttu-id="09432-131">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="09432-131">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="09432-132">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="09432-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="09432-133">Typsystem</span><span class="sxs-lookup"><span data-stu-id="09432-133">Type System</span></span>](type-system-entity-sql.md)
