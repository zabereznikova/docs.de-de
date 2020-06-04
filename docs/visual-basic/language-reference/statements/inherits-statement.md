---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 5d88a01f90bc91a88229d19aa2368f8c71075b2f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404498"
---
# <a name="inherits-statement"></a><span data-ttu-id="77be2-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="77be2-102">Inherits Statement</span></span>
<span data-ttu-id="77be2-103">Bewirkt, dass die aktuelle Klasse oder Schnittstelle die Attribute, Variablen, Eigenschaften, Prozeduren und Ereignisse von einer anderen Klasse oder Gruppe von Schnittstellen erbt.</span><span class="sxs-lookup"><span data-stu-id="77be2-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77be2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77be2-104">Syntax</span></span>  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="77be2-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="77be2-105">Parts</span></span>  
  
|<span data-ttu-id="77be2-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="77be2-106">Term</span></span>|<span data-ttu-id="77be2-107">Definition</span><span class="sxs-lookup"><span data-stu-id="77be2-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="77be2-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77be2-108">Required.</span></span> <span data-ttu-id="77be2-109">Der Name der Klasse, von der diese Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="77be2-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="77be2-110">Oder</span><span class="sxs-lookup"><span data-stu-id="77be2-110">-or-</span></span><br /><br /> <span data-ttu-id="77be2-111">Die Namen der Schnittstellen, von denen diese Schnittstelle abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="77be2-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="77be2-112">Trennen Sie mehrere Namen mithilfe von Kommas.</span><span class="sxs-lookup"><span data-stu-id="77be2-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77be2-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="77be2-113">Remarks</span></span>  
 <span data-ttu-id="77be2-114">Bei Verwendung der `Inherits` Anweisung muss es sich bei der Anweisung um die erste nicht leere Zeile, die keine Kommentarzeile in einer Klassen-oder Schnittstellen Definition handelt.</span><span class="sxs-lookup"><span data-stu-id="77be2-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="77be2-115">Er sollte unmittelbar auf die- `Class` oder- `Interface` Anweisung folgen.</span><span class="sxs-lookup"><span data-stu-id="77be2-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="77be2-116">Sie können `Inherits` nur in einer Klasse oder Schnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="77be2-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="77be2-117">Dies bedeutet, dass der Deklarations Kontext für eine Vererbung keine Quelldatei, ein Namespace, eine Struktur, ein Modul, eine Prozedur oder ein Block sein kann.</span><span class="sxs-lookup"><span data-stu-id="77be2-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="77be2-118">Regeln</span><span class="sxs-lookup"><span data-stu-id="77be2-118">Rules</span></span>  
  
- <span data-ttu-id="77be2-119">**Klassen Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="77be2-119">**Class Inheritance.**</span></span> <span data-ttu-id="77be2-120">Wenn eine Klasse die- `Inherits` Anweisung verwendet, können Sie nur eine Basisklasse angeben.</span><span class="sxs-lookup"><span data-stu-id="77be2-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="77be2-121">Eine Klasse kann nicht von einer Klasse erben, die darin geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="77be2-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="77be2-122">**Schnittstellen Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="77be2-122">**Interface Inheritance.**</span></span> <span data-ttu-id="77be2-123">Wenn eine Schnittstelle die- `Inherits` Anweisung verwendet, können Sie eine oder mehrere Basis Schnittstellen angeben.</span><span class="sxs-lookup"><span data-stu-id="77be2-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="77be2-124">Sie können von zwei Schnittstellen erben, auch wenn Sie jeweils einen Member mit demselben Namen definieren.</span><span class="sxs-lookup"><span data-stu-id="77be2-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="77be2-125">Wenn Sie dies tun, muss der implementierende Code die namens Qualifizierung verwenden, um anzugeben, welcher Member implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="77be2-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="77be2-126">Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer restriktiveren Zugriffsebene erben.</span><span class="sxs-lookup"><span data-stu-id="77be2-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="77be2-127">Beispielsweise kann eine- `Public` Schnittstelle nicht von einer- `Friend` Schnittstelle erben.</span><span class="sxs-lookup"><span data-stu-id="77be2-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="77be2-128">Eine Schnittstelle kann nicht von einer Schnittstelle erben, die darin geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="77be2-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="77be2-129">Ein Beispiel für die Klassen Vererbung in der .NET Framework ist die- <xref:System.ArgumentException> Klasse, die von der-Klasse erbt <xref:System.SystemException> .</span><span class="sxs-lookup"><span data-stu-id="77be2-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="77be2-130">Dies bietet <xref:System.ArgumentException> alle vordefinierten Eigenschaften und Prozeduren, die für System Ausnahmen erforderlich sind, wie z <xref:System.Exception.Message%2A> . b. die-Eigenschaft und die- <xref:System.Exception.ToString%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="77be2-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="77be2-131">Ein Beispiel für die Schnittstellen Vererbung in der .NET Framework ist die- <xref:System.Collections.ICollection> Schnittstelle, die von der- <xref:System.Collections.IEnumerable> Schnittstelle erbt.</span><span class="sxs-lookup"><span data-stu-id="77be2-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="77be2-132">Dies bewirkt <xref:System.Collections.ICollection> , dass die Definition des Enumerators erbt, der zum Durchlaufen einer Auflistung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="77be2-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77be2-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77be2-133">Example</span></span>  
 <span data-ttu-id="77be2-134">Im folgenden Beispiel wird die- `Inherits` Anweisung verwendet, um anzuzeigen, wie eine Klasse mit dem Namen `thisClass` alle Member einer Basisklasse mit dem Namen erben kann `anotherClass` .</span><span class="sxs-lookup"><span data-stu-id="77be2-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="77be2-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77be2-135">Example</span></span>  
 <span data-ttu-id="77be2-136">Das folgende Beispiel zeigt die Vererbung mehrerer Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="77be2-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="77be2-137">Die-Schnittstelle `thisInterface` enthält jetzt alle Definitionen in den <xref:System.IComparable> <xref:System.IDisposable> -,-und- <xref:System.IFormattable> Schnittstellen, die geerbte Member jeweils für typspezifischen Vergleich von zwei-Objekten bereitstellen, zugeordnete Ressourcen freigeben und den Wert eines Objekts als Ausdrücken `String` .</span><span class="sxs-lookup"><span data-stu-id="77be2-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="77be2-138">Eine Klasse, die implementiert, `thisInterface` muss jeden Member jeder Basisschnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="77be2-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77be2-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77be2-139">See also</span></span>

- [<span data-ttu-id="77be2-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="77be2-140">MustInherit</span></span>](../modifiers/mustinherit.md)
- [<span data-ttu-id="77be2-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="77be2-141">NotInheritable</span></span>](../modifiers/notinheritable.md)
- [<span data-ttu-id="77be2-142">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="77be2-142">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="77be2-143">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="77be2-143">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="77be2-144">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="77be2-144">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
