---
title: virtual (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
dev_langs:
- CSharp
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 24ca77a0a645a17c0223437e73539bc04ba80f23
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="virtual-c-reference"></a><span data-ttu-id="4d3b8-102">virtual (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4d3b8-102">virtual (C# Reference)</span></span>
<span data-ttu-id="4d3b8-103">Das Schlüsselwort `virtual` wird zum Ändern einer Methoden-, Eigenschaften-, Indexer- oder Ereignisdeklaration verwendet, und lässt zu, dass sie in einer abgeleiteten Klasse außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="4d3b8-104">Diese Methode kann z.B. von jeder Klasse, die sie erbt, überschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="4d3b8-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="4d3b8-105">Die Implementierung eines virtuellen Members kann durch einen [overriding member](../../../csharp/language-reference/keywords/override.md) (überschreibender Member) in einer abgeleiteten Klasse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="4d3b8-106">Weitere Informationen zur Verwendung des `virtual`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="4d3b8-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d3b8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d3b8-107">Remarks</span></span>  
 <span data-ttu-id="4d3b8-108">Wenn eine virtuelle Methode aufgerufen wird, wird der Laufzeittyp des Objekts auf einen überschreibenden Member überprüft.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="4d3b8-109">Der überschreibende Member in der abgeleitetsten Klasse (bei dem es sich um den ursprünglichen Member handeln könnte) wird aufgerufen, wenn keine abgeleitete Klasse den Member außer Kraft gesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="4d3b8-110">Standardmäßig sind Methoden nicht virtuell.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="4d3b8-111">Sie können keine nicht virtuelle Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="4d3b8-112">Sie können den Modifizierer `virtual` nicht mit den Modifizierern `static`, `abstract, private` oder `override` verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-112">You cannot use the `virtual` modifier with the `static`, `abstract, private`, or `override` modifiers.</span></span> <span data-ttu-id="4d3b8-113">Im folgenden Beispiel wird eine virtuelle Methode gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4d3b8-113">The following example shows a virtual property:</span></span>  
  
 <span data-ttu-id="4d3b8-114">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4d3b8-114">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]</span></span>  
  
 <span data-ttu-id="4d3b8-115">Virtuelle Eigenschaften verhalten sich wie abstrakte Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-115">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="4d3b8-116">Es ist unzulässig, den `virtual`-Modifizierer für eine statische Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-116">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="4d3b8-117">Eine virtuelle vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer `override` verwendet, außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-117">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d3b8-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d3b8-118">Example</span></span>  
 <span data-ttu-id="4d3b8-119">In diesem Beispiel enthält die Klasse `Shape` die zwei Koordinaten `x` und `y` und die virtuelle Methode `Area()`.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-119">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="4d3b8-120">Andere Formklassen, z.B. `Circle`, `Cylinder` und `Sphere` erben die Klasse `Shape`. Die Oberfläche wird für jede Abbildung berechnet.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-120">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="4d3b8-121">Jede abgeleitete Klasse verfügt über Ihre eigene Überschreibungsimplementierung von `Area()`.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-121">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="4d3b8-122">Beachten Sie, dass die geerbten Klassen `Circle`, `Sphere` und `Cylinder` alle Konstruktoren verwenden, die die Basisklasse initialisieren, wie in der folgenden Deklaration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-122">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="4d3b8-123">Das folgende Programm berechnet und zeigt den entsprechenden Bereich für jede Abbildung durch Aufruf der entsprechenden Implementierung der `Area()`-Methode gemäß dem Objekt, das der Methode zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4d3b8-123">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 <span data-ttu-id="4d3b8-124">[!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4d3b8-124">[!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4d3b8-125">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4d3b8-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d3b8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d3b8-126">See Also</span></span>  
 <span data-ttu-id="4d3b8-127">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4d3b8-128">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4d3b8-129">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-129">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="4d3b8-130">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4d3b8-131">[Polymorphismus](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-131">[Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span></span>  
 <span data-ttu-id="4d3b8-132">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-132">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="4d3b8-133">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="4d3b8-133">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="4d3b8-134">new</span><span class="sxs-lookup"><span data-stu-id="4d3b8-134">new</span></span>](../../../csharp/language-reference/keywords/new.md)

