---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 0bda03d3c01356317fbcc56d44199ff4f9484b5b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816563"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="828de-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="828de-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="828de-103">Gibt an, dass eine Klasse nur als Basisklasse verwendet werden kann und ein Objekt kann nicht direkt daraus erstellen.</span><span class="sxs-lookup"><span data-stu-id="828de-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="828de-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="828de-104">Remarks</span></span>  
 <span data-ttu-id="828de-105">Der Zweck einer *Basisklasse* (auch bekannt als ein *abstrakte Klasse*) besteht darin, Funktionen zu definieren, die für alle Klassen, die davon abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="828de-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="828de-106">Dies erspart die abgeleiteten Klassen, die gängigen Elemente neu zu definieren.</span><span class="sxs-lookup"><span data-stu-id="828de-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="828de-107">In einigen Fällen diesen häufig verwendeten Funktionen ist nicht umfassend genug, um ein Objekt verwendbar zu machen, und jede abgeleitete Klasse definiert die fehlende Funktion.</span><span class="sxs-lookup"><span data-stu-id="828de-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="828de-108">In diesem Fall möchten Sie den verwendeten Code zum Erstellen von Objekten nur von den abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="828de-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="828de-109">Verwenden Sie `MustInherit` in der Basisklasse, dies durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="828de-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="828de-110">Eine andere Verwendung von einem `MustInherit` Klasse ist, um eine Variable auf einen Satz verwandter Klassen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="828de-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="828de-111">Sie können eine Basisklasse definieren und diese verwandten Klassen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="828de-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="828de-112">Die Basisklasse muss keine Funktionen, die auf alle abgeleiteten Klassen bereitstellen, aber als einen Filter für das Zuweisen von Werten zu Variablen dienen.</span><span class="sxs-lookup"><span data-stu-id="828de-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="828de-113">Wenn im verwendeten Code eine Variable als Basisklasse deklariert können Visual Basic Sie nur ein Objekt eine abgeleitete Klasse diese Variable zuweisen.</span><span class="sxs-lookup"><span data-stu-id="828de-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="828de-114">.NET Framework definiert verschiedene `MustInherit` Klassen, u. a. <xref:System.Array>, <xref:System.Enum>, und <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="828de-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="828de-115"><xref:System.ValueType> ist ein Beispiel für eine Basisklasse, die eine Variable beschränkt.</span><span class="sxs-lookup"><span data-stu-id="828de-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="828de-116">Alle Werttypen werden von <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="828de-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="828de-117">Wenn Sie eine Variable deklarieren <xref:System.ValueType>, Sie können diese Variable nur Werttypen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="828de-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="828de-118">Regeln</span><span class="sxs-lookup"><span data-stu-id="828de-118">Rules</span></span>  
  
-   <span data-ttu-id="828de-119">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="828de-119">**Declaration Context.**</span></span> <span data-ttu-id="828de-120">Sie können `MustInherit` nur in einem `Class` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="828de-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
-   <span data-ttu-id="828de-121">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="828de-121">**Combined Modifiers.**</span></span> <span data-ttu-id="828de-122">Sie können keine angeben `MustInherit` zusammen mit `NotInheritable` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="828de-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="828de-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="828de-123">Example</span></span>  
 <span data-ttu-id="828de-124">Das folgende Beispiel veranschaulicht die erzwungene Vererbung und erzwungene überschreiben.</span><span class="sxs-lookup"><span data-stu-id="828de-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="828de-125">Die Basisklasse `shape` definiert eine Variable `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="828de-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="828de-126">Die Klassen `circle` und `square` abgeleitet `shape`.</span><span class="sxs-lookup"><span data-stu-id="828de-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="828de-127">Sie erben die Definition der `acrossLine`, jedoch müssen sie die Funktion definieren `area` , da die Berechnung für jede Art von Form unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="828de-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="828de-128">Sie können deklarieren, `shape1` und `shape2` Typ `shape`.</span><span class="sxs-lookup"><span data-stu-id="828de-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="828de-129">Sie können nicht jedoch ein Objekt aus erstellen `shape` weil. die Funktionen der fehlt `area` und markiert `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="828de-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="828de-130">Da sie als deklariert werden `shape`, die Variablen `shape1` und `shape2` auf Objekte beschränkt sind, die von den abgeleiteten Klassen `circle` und `square`.</span><span class="sxs-lookup"><span data-stu-id="828de-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="828de-131">Visual Basic erlaubt Ihnen kein anderes Objekt zuweisen, diese Variablen, die Ihnen ein hohes Maß an typsicherheit bietet.</span><span class="sxs-lookup"><span data-stu-id="828de-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="828de-132">Verwendung</span><span class="sxs-lookup"><span data-stu-id="828de-132">Usage</span></span>  
 <span data-ttu-id="828de-133">Die `MustInherit` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="828de-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="828de-134">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="828de-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="828de-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="828de-135">See also</span></span>

- [<span data-ttu-id="828de-136">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="828de-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="828de-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="828de-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="828de-138">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="828de-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="828de-139">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="828de-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
