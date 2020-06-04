---
title: MustInherit
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
ms.openlocfilehash: 84df7a5cfdad3b5bc6764675725a5d0cb402b0b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396206"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="33ee5-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33ee5-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="33ee5-103">Gibt an, dass eine Klasse nur als Basisklasse verwendet werden kann und dass Sie kein Objekt direkt aus der Klasse erstellen können.</span><span class="sxs-lookup"><span data-stu-id="33ee5-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33ee5-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="33ee5-104">Remarks</span></span>  
 <span data-ttu-id="33ee5-105">Der Zweck einer *Basisklasse* (auch als *abstrakte Klasse*bezeichnet) besteht darin, die Funktionalität zu definieren, die allen von ihr abgeleiteten Klassen gemeinsam ist.</span><span class="sxs-lookup"><span data-stu-id="33ee5-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="33ee5-106">Dadurch werden die abgeleiteten Klassen daran bewahrt, die gemeinsamen Elemente neu zu definieren.</span><span class="sxs-lookup"><span data-stu-id="33ee5-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="33ee5-107">In einigen Fällen ist diese gängige Funktionalität nicht ausreichend, um ein verwendbares Objekt zu erstellen, und jede abgeleitete Klasse definiert die fehlende Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="33ee5-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="33ee5-108">In einem solchen Fall möchten Sie, dass der verarbeitende Code nur Objekte aus den abgeleiteten Klassen erstellt.</span><span class="sxs-lookup"><span data-stu-id="33ee5-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="33ee5-109">Verwenden Sie für `MustInherit` die Basisklasse, um dies zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="33ee5-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="33ee5-110">Eine andere Verwendung einer- `MustInherit` Klasse besteht darin, eine Variable auf einen Satz verwandter Klassen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="33ee5-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="33ee5-111">Sie können eine Basisklasse definieren und alle diese verknüpften Klassen davon ableiten.</span><span class="sxs-lookup"><span data-stu-id="33ee5-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="33ee5-112">Die Basisklasse muss keine Funktionalität bereitstellen, die allen abgeleiteten Klassen gemeinsam ist. Sie kann jedoch als Filter zum Zuweisen von Werten zu Variablen dienen.</span><span class="sxs-lookup"><span data-stu-id="33ee5-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="33ee5-113">Wenn in Ihrem verarbeitenden Code eine Variable als Basisklasse deklariert wird, können Sie mit Visual Basic nur ein Objekt aus einer der abgeleiteten Klassen der Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="33ee5-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="33ee5-114">Der-.NET Framework definiert mehrere `MustInherit` Klassen, darunter <xref:System.Array> , <xref:System.Enum> und <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="33ee5-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="33ee5-115"><xref:System.ValueType>ist ein Beispiel für eine Basisklasse, die eine Variable einschränkt.</span><span class="sxs-lookup"><span data-stu-id="33ee5-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="33ee5-116">Alle Werttypen werden von abgeleitet <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="33ee5-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="33ee5-117">Wenn Sie eine Variable als deklarieren <xref:System.ValueType> , können Sie dieser Variablen nur Werttypen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="33ee5-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="33ee5-118">Regeln</span><span class="sxs-lookup"><span data-stu-id="33ee5-118">Rules</span></span>  
  
- <span data-ttu-id="33ee5-119">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="33ee5-119">**Declaration Context.**</span></span> <span data-ttu-id="33ee5-120">Sie können `MustInherit` nur in einer- `Class` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="33ee5-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="33ee5-121">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="33ee5-121">**Combined Modifiers.**</span></span> <span data-ttu-id="33ee5-122">Sie können nicht `MustInherit` mit `NotInheritable` in der gleichen Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="33ee5-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33ee5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33ee5-123">Example</span></span>  
 <span data-ttu-id="33ee5-124">Das folgende Beispiel veranschaulicht sowohl die erzwungene Vererbung als auch das erzwungene überschreiben.</span><span class="sxs-lookup"><span data-stu-id="33ee5-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="33ee5-125">Die-Basisklasse `shape` definiert eine Variable `acrossLine` .</span><span class="sxs-lookup"><span data-stu-id="33ee5-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="33ee5-126">Die Klassen `circle` und werden `square` von abgeleitet `shape` .</span><span class="sxs-lookup"><span data-stu-id="33ee5-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="33ee5-127">Sie erben die Definition von `acrossLine` , müssen jedoch die-Funktion definieren, `area` da diese Berechnung für jede Art von Form unterschiedlich ist.</span><span class="sxs-lookup"><span data-stu-id="33ee5-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="33ee5-128">Sie können `shape1` und `shape2` den Typ deklarieren `shape` .</span><span class="sxs-lookup"><span data-stu-id="33ee5-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="33ee5-129">Es ist jedoch nicht möglich, ein Objekt aus zu erstellen, `shape` da es nicht über die Funktionen der-Funktion verfügt `area` und als gekennzeichnet ist `MustInherit` .</span><span class="sxs-lookup"><span data-stu-id="33ee5-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="33ee5-130">Da Sie als deklariert werden `shape` , sind die Variablen `shape1` und `shape2` auf Objekte aus den abgeleiteten Klassen `circle` und beschränkt `square` .</span><span class="sxs-lookup"><span data-stu-id="33ee5-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="33ee5-131">In Visual Basic können Sie diesen Variablen keine anderen Objekte zuweisen, was Ihnen ein hohes Maß an Typsicherheit bietet.</span><span class="sxs-lookup"><span data-stu-id="33ee5-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="33ee5-132">Verwendung</span><span class="sxs-lookup"><span data-stu-id="33ee5-132">Usage</span></span>  
 <span data-ttu-id="33ee5-133">Der- `MustInherit` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="33ee5-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="33ee5-134">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="33ee5-134">Class Statement</span></span>](../statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="33ee5-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33ee5-135">See also</span></span>

- [<span data-ttu-id="33ee5-136">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="33ee5-136">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="33ee5-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="33ee5-137">NotInheritable</span></span>](notinheritable.md)
- [<span data-ttu-id="33ee5-138">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="33ee5-138">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="33ee5-139">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="33ee5-139">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
