---
title: Inherits-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: c39272d53fea136c83a5a09444b65a594fe3b7a7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625508"
---
# <a name="inherits-statement"></a><span data-ttu-id="1b1d3-102">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="1b1d3-102">Inherits Statement</span></span>
<span data-ttu-id="1b1d3-103">Bewirkt, dass die aktuelle Klasse bzw. Schnittstelle der Attribute, Variablen, Eigenschaften, Prozeduren und Ereignisse von einer anderen Klasse oder Gruppe von Schnittstellen erbt.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-103">Causes the current class or interface to inherit the attributes, variables, properties, procedures, and events from another class or set of interfaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b1d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b1d3-104">Syntax</span></span>  
  
```  
Inherits basetypenames  
```  
  
## <a name="parts"></a><span data-ttu-id="1b1d3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1b1d3-105">Parts</span></span>  
  
|<span data-ttu-id="1b1d3-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="1b1d3-106">Term</span></span>|<span data-ttu-id="1b1d3-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1b1d3-107">Definition</span></span>|  
|---|---|  
|`basetypenames`|<span data-ttu-id="1b1d3-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-108">Required.</span></span> <span data-ttu-id="1b1d3-109">Der Name der Klasse, aus der dieser Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-109">The name of the class from which this class derives.</span></span><br /><br /> <span data-ttu-id="1b1d3-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="1b1d3-110">-or-</span></span><br /><br /> <span data-ttu-id="1b1d3-111">Die Namen der Schnittstellen, die von denen diese Schnittstelle abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-111">The names of the interfaces from which this interface derives.</span></span> <span data-ttu-id="1b1d3-112">Verwenden Sie Kommas zum Trennen mehrere Namen ein.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-112">Use commas to separate multiple names.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b1d3-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b1d3-113">Remarks</span></span>  
 <span data-ttu-id="1b1d3-114">Wenn verwendet, die `Inherits` -Anweisung muss die erste nicht leere, nicht kommentierten Zeile in der Definition einer Klasse oder Schnittstelle sein.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-114">If used, the `Inherits` statement must be the first non-blank, non-comment line in a class or interface definition.</span></span> <span data-ttu-id="1b1d3-115">Es sollte unmittelbar folgen der `Class` oder `Interface` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-115">It should immediately follow the `Class` or `Interface` statement.</span></span>  
  
 <span data-ttu-id="1b1d3-116">Sie können `Inherits` nur in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-116">You can use `Inherits` only in a class or interface.</span></span> <span data-ttu-id="1b1d3-117">Dies bedeutet, dass der Deklarationskontext für Vererbung eine Quelldatei, Namespace, Struktur, Modul, Prozedur oder Block kann nicht.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-117">This means the declaration context for an inheritance cannot be a source file, namespace, structure, module, procedure, or block.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1b1d3-118">Regeln</span><span class="sxs-lookup"><span data-stu-id="1b1d3-118">Rules</span></span>  
  
- <span data-ttu-id="1b1d3-119">**Klassenvererbung.**</span><span class="sxs-lookup"><span data-stu-id="1b1d3-119">**Class Inheritance.**</span></span> <span data-ttu-id="1b1d3-120">Wenn eine Klasse verwendet die `Inherits` -Anweisung können Sie nur eine Basisklasse angeben.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-120">If a class uses the `Inherits` statement, you can specify only one base class.</span></span>  
  
     <span data-ttu-id="1b1d3-121">Eine Klasse kann nicht von einer Klasse, die in ihr geschachtelt ist, erben.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-121">A class cannot inherit from a class nested within it.</span></span>  
  
- <span data-ttu-id="1b1d3-122">**Schnittstellenvererbung.**</span><span class="sxs-lookup"><span data-stu-id="1b1d3-122">**Interface Inheritance.**</span></span> <span data-ttu-id="1b1d3-123">Wenn eine Schnittstelle verwendet die `Inherits` -Anweisung können Sie einem oder mehreren Basisschnittstellen angeben.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-123">If an interface uses the `Inherits` statement, you can specify one or more base interfaces.</span></span> <span data-ttu-id="1b1d3-124">Sie können über zwei Schnittstellen erben, auch wenn sie jeweils einen Member mit demselben Namen definieren.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-124">You can inherit from two interfaces even if they each define a member with the same name.</span></span> <span data-ttu-id="1b1d3-125">Wenn Sie dies tun, muss der implementierende Code Namensqualifikation verwenden Sie zum Angeben von der Members implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-125">If you do so, the implementing code must use name qualification to specify which member it is implementing.</span></span>  
  
     <span data-ttu-id="1b1d3-126">Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer stärker einschränkende Zugriffsebene erben.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-126">An interface cannot inherit from another interface with a more restrictive access level.</span></span> <span data-ttu-id="1b1d3-127">Z. B. eine `Public` Schnittstelle kann nicht erben von einem `Friend` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-127">For example, a `Public` interface cannot inherit from a `Friend` interface.</span></span>  
  
     <span data-ttu-id="1b1d3-128">Eine Schnittstelle kann nicht von einer Schnittstelle, die in ihr geschachtelt ist, erben.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-128">An interface cannot inherit from an interface nested within it.</span></span>  
  
 <span data-ttu-id="1b1d3-129">Ein Beispiel für klassenvererbung in .NET Framework ist die <xref:System.ArgumentException> -Klasse, die erbt die <xref:System.SystemException> Klasse.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-129">An example of class inheritance in the .NET Framework is the <xref:System.ArgumentException> class, which inherits from the <xref:System.SystemException> class.</span></span> <span data-ttu-id="1b1d3-130">Dies bietet auf <xref:System.ArgumentException> alle vordefinierte Eigenschaften und Prozeduren, die Systemausnahmen, erforderlich sind, z. B. die <xref:System.Exception.Message%2A> Eigenschaft und die <xref:System.Exception.ToString%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-130">This provides to <xref:System.ArgumentException> all the predefined properties and procedures required by system exceptions, such as the <xref:System.Exception.Message%2A> property and the <xref:System.Exception.ToString%2A> method.</span></span>  
  
 <span data-ttu-id="1b1d3-131">Ein Beispiel für schnittstellenvererbung in .NET Framework ist die <xref:System.Collections.ICollection> -Schnittstelle, die erbt die <xref:System.Collections.IEnumerable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-131">An example of interface inheritance in the .NET Framework is the <xref:System.Collections.ICollection> interface, which inherits from the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="1b1d3-132">Dies bewirkt, dass <xref:System.Collections.ICollection> erben von der Definition der Enumerator zum Durchlaufen einer Auflistung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-132">This causes <xref:System.Collections.ICollection> to inherit the definition of the enumerator required to traverse a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b1d3-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b1d3-133">Example</span></span>  
 <span data-ttu-id="1b1d3-134">Im folgenden Beispiel wird die `Inherits` Anweisung, um zu zeigen, wie eine Klasse namens `thisClass` können alle Member der Basisklasse erben `anotherClass`.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-134">The following example uses the `Inherits` statement to show how a class named `thisClass` can inherit all the members of a base class named `anotherClass`.</span></span>  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="1b1d3-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b1d3-135">Example</span></span>  
 <span data-ttu-id="1b1d3-136">Das folgende Beispiel zeigt die Vererbung von mehreren Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-136">The following example shows inheritance of multiple interfaces.</span></span>  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 <span data-ttu-id="1b1d3-137">Die Schnittstelle, die mit dem Namen `thisInterface` enthält jetzt alle Definitionen in der <xref:System.IComparable>, <xref:System.IDisposable>, und <xref:System.IFormattable> Schnittstellen die geerbten Member bzw. ein typenspezifisches Vergleich von zwei Objekten Freigeben von zugeordneten Ressourcen , und deren Ausdruck des Werts eines Objekts als ein `String`.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-137">The interface named `thisInterface` now includes all the definitions in the <xref:System.IComparable>, <xref:System.IDisposable>, and <xref:System.IFormattable> interfaces The inherited members provide respectively for type-specific comparison of two objects, releasing allocated resources, and expressing the value of an object as a `String`.</span></span> <span data-ttu-id="1b1d3-138">Eine Klasse, die implementiert `thisInterface` müssen alle Member jeder Basisschnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="1b1d3-138">A class that implements `thisInterface` must implement every member of every base interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1d3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b1d3-139">See also</span></span>

- [<span data-ttu-id="1b1d3-140">MustInherit</span><span class="sxs-lookup"><span data-stu-id="1b1d3-140">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="1b1d3-141">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="1b1d3-141">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="1b1d3-142">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="1b1d3-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="1b1d3-143">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="1b1d3-143">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="1b1d3-144">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b1d3-144">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
