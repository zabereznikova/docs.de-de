---
title: virtual (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: af5b7e3efdc98910ebbe7e061eba250cbe2d0c50
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207348"
---
# <a name="virtual-c-reference"></a><span data-ttu-id="26808-102">virtual (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="26808-102">virtual (C# Reference)</span></span>
<span data-ttu-id="26808-103">Das Schlüsselwort `virtual` wird zum Ändern einer Methoden-, Eigenschaften-, Indexer- oder Ereignisdeklaration verwendet, und lässt zu, dass sie in einer abgeleiteten Klasse außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="26808-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="26808-104">Diese Methode kann z.B. von jeder Klasse, die sie erbt, überschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="26808-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```csharp  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="26808-105">Die Implementierung eines virtuellen Members kann durch einen [overriding member](../../../csharp/language-reference/keywords/override.md) (überschreibender Member) in einer abgeleiteten Klasse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="26808-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="26808-106">Weitere Informationen zur Verwendung des `virtual`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="26808-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26808-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26808-107">Remarks</span></span>  
 <span data-ttu-id="26808-108">Wenn eine virtuelle Methode aufgerufen wird, wird der Laufzeittyp des Objekts auf einen überschreibenden Member überprüft.</span><span class="sxs-lookup"><span data-stu-id="26808-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="26808-109">Der überschreibende Member in der abgeleitetsten Klasse (bei dem es sich um den ursprünglichen Member handeln könnte) wird aufgerufen, wenn keine abgeleitete Klasse den Member außer Kraft gesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="26808-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="26808-110">Standardmäßig sind Methoden nicht virtuell.</span><span class="sxs-lookup"><span data-stu-id="26808-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="26808-111">Sie können keine nicht virtuelle Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="26808-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="26808-112">Sie können den Modifizierer `virtual` nicht mit den Modifizierern `static`, `abstract`, `private` oder `override` verwenden.</span><span class="sxs-lookup"><span data-stu-id="26808-112">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="26808-113">Im folgenden Beispiel wird eine virtuelle Methode gezeigt:</span><span class="sxs-lookup"><span data-stu-id="26808-113">The following example shows a virtual property:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 <span data-ttu-id="26808-114">Virtuelle Eigenschaften verhalten sich wie abstrakte Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.</span><span class="sxs-lookup"><span data-stu-id="26808-114">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="26808-115">Es ist unzulässig, den `virtual`-Modifizierer für eine statische Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="26808-115">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="26808-116">Eine virtuelle vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer `override` verwendet, außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="26808-116">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26808-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26808-117">Example</span></span>  
 <span data-ttu-id="26808-118">In diesem Beispiel enthält die Klasse `Shape` die zwei Koordinaten `x` und `y` und die virtuelle Methode `Area()`.</span><span class="sxs-lookup"><span data-stu-id="26808-118">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="26808-119">Andere Formklassen, z.B. `Circle`, `Cylinder` und `Sphere` erben die Klasse `Shape`. Die Oberfläche wird für jede Abbildung berechnet.</span><span class="sxs-lookup"><span data-stu-id="26808-119">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="26808-120">Jede abgeleitete Klasse verfügt über ihre eigene Überschreibungsimplementierung von `Area()`.</span><span class="sxs-lookup"><span data-stu-id="26808-120">Each derived class has its own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="26808-121">Beachten Sie, dass die geerbten Klassen `Circle`, `Sphere` und `Cylinder` alle Konstruktoren verwenden, die die Basisklasse initialisieren, wie in der folgenden Deklaration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="26808-121">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```csharp  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="26808-122">Das folgende Programm berechnet und zeigt den entsprechenden Bereich für jede Abbildung durch Aufruf der entsprechenden Implementierung der `Area()`-Methode gemäß dem Objekt, das der Methode zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="26808-122">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="26808-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="26808-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26808-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26808-124">See Also</span></span>  
 [<span data-ttu-id="26808-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="26808-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="26808-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="26808-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="26808-127">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="26808-127">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="26808-128">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="26808-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="26808-129">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="26808-129">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="26808-130">abstract</span><span class="sxs-lookup"><span data-stu-id="26808-130">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="26808-131">override</span><span class="sxs-lookup"><span data-stu-id="26808-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="26808-132">new</span><span class="sxs-lookup"><span data-stu-id="26808-132">new</span></span>](../../../csharp/language-reference/keywords/new.md)
