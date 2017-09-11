---
title: Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0788ea0778b3f8b846231fc2408938b2236314c9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="8416b-102">Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8416b-102">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="8416b-103">Das Schlüsselwort [abstract](../../../csharp/language-reference/keywords/abstract.md) ermöglicht die Erstellung von Klassen und [Klassenmembern](../../../csharp/language-reference/keywords/class.md), die unvollständig sind und in einer abgeleiteten Klasse implementiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8416b-103">The [abstract](../../../csharp/language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../../csharp/language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="8416b-104">Mit dem Schlüsselwort [sealed](../../../csharp/language-reference/keywords/sealed.md) können Sie die Vererbung von Klassen oder bestimmten Klassenmembern unterbinden, die zuvor als [virtuell](../../../csharp/language-reference/keywords/virtual.md) gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="8416b-104">The [sealed](../../../csharp/language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="8416b-105">Abstrakte Klassen und Klassenmember</span><span class="sxs-lookup"><span data-stu-id="8416b-105">Abstract Classes and Class Members</span></span>  
 <span data-ttu-id="8416b-106">Klassen können durch Festlegen des Schlüsselworts `abstract` vor der Klassendefinition als abstrakt deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="8416b-106">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="8416b-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8416b-107">For example:</span></span>  
  
 <span data-ttu-id="8416b-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8416b-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span></span>  
  
 <span data-ttu-id="8416b-109">Eine abstrakte Klasse darf nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="8416b-109">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="8416b-110">Der Zweck einer abstrakten Klasse ist die Bereitstellung einer allgemeinen Definition einer Basisklasse, die für mehrere abgeleitete Klassen freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8416b-110">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="8416b-111">Eine Klassenbibliothek kann beispielsweise eine abstrakte Klasse definieren, die als Parameter für ihre Funktionen verwendet wird. Programmierer, die diese Bibliothek verwenden, benötigen ihre eigene Implementierung der Klasse, die sie von ihr ableiten können.</span><span class="sxs-lookup"><span data-stu-id="8416b-111">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="8416b-112">Abstrakte Klassen können auch abstrakte Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="8416b-112">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="8416b-113">Zu diesem Zweck wird das Schlüsselwort `abstract` vor dem Rückgabetyp der Methode einfügt.</span><span class="sxs-lookup"><span data-stu-id="8416b-113">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="8416b-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8416b-114">For example:</span></span>  
  
 <span data-ttu-id="8416b-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8416b-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span></span>  
  
 <span data-ttu-id="8416b-116">Abstrakte Methoden verfügen über keine Implementierung, deshalb folgt der Methodendefinition ein Semikolon statt eines normalen Methodenblocks.</span><span class="sxs-lookup"><span data-stu-id="8416b-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="8416b-117">Von der abstrakten Klasse abgeleitete Klassen müssen alle abstrakten Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="8416b-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="8416b-118">Wenn eine abstrakte Klasse eine virtuelle Methode von einer Basisklasse erbt, kann sie die virtuelle Methode mit einer abstrakten Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8416b-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="8416b-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8416b-119">For example:</span></span>  
  
 <span data-ttu-id="8416b-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8416b-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span></span>  
  
 <span data-ttu-id="8416b-121">Wenn eine `virtual`-Methode als `abstract` deklariert ist, bleibt sie für alle Klassen virtuell, die von der abstrakten Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="8416b-121">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="8416b-122">Eine Klasse, die eine abstrakte Methode erbt, kann nicht auf die ursprüngliche Implementierung der Methode zugreifen. Im vorherigen Beispiel konnte `DoWork` auf Klasse F `DoWork` auf Klasse D nicht aufrufen. So kann eine abstrakte Klasse abgeleitete Klassen dazu zwingen, neue Methodenimplementierungen für virtuelle Methoden bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8416b-122">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="8416b-123">Versiegelte Klassen und Klassenmember</span><span class="sxs-lookup"><span data-stu-id="8416b-123">Sealed Classes and Class Members</span></span>  
 <span data-ttu-id="8416b-124">Klassen können durch Festlegen des Schlüsselworts `sealed` vor der Klassendefinition als [sealed](../../../csharp/language-reference/keywords/sealed.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="8416b-124">Classes can be declared as [sealed](../../../csharp/language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="8416b-125">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8416b-125">For example:</span></span>  
  
 <span data-ttu-id="8416b-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8416b-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span></span>  
  
 <span data-ttu-id="8416b-127">Eine versiegelte Klasse kann nicht als Basisklasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8416b-127">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="8416b-128">Aus diesem Grund kann sie auch keine abstrakte Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="8416b-128">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="8416b-129">Von versiegelten Klassen kann nicht abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8416b-129">Sealed classes prevent derivation.</span></span> <span data-ttu-id="8416b-130">Weil sie nicht als Basisklasse verwendet werden können, können Aufrufe an versiegelte Klassenmember durch Laufzeitoptimierungen etwas beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="8416b-130">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="8416b-131">Methoden, Indexer, Eigenschaften oder Ereignisse einer abgeleiteten Klasse, die einen virtuellen Member der Basisklasse überschreiben, können diesen Member als versiegelt deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8416b-131">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="8416b-132">Damit wird der virtuelle Aspekt des Members für jede weitere abgeleitete Klasse aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="8416b-132">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="8416b-133">Dazu wird in die Klassenmemberdeklaration das Schlüsselwort `sealed` vor dem Schlüsselwort [override](../../../csharp/language-reference/keywords/override.md) eingefügt.</span><span class="sxs-lookup"><span data-stu-id="8416b-133">This is accomplished by putting the `sealed` keyword before the [override](../../../csharp/language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="8416b-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8416b-134">For example:</span></span>  
  
 <span data-ttu-id="8416b-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8416b-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8416b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8416b-136">See Also</span></span>  
 <span data-ttu-id="8416b-137">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8416b-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8416b-138">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="8416b-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="8416b-139">[Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="8416b-139">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="8416b-140">[Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="8416b-140">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="8416b-141">[Felder](../../../csharp/programming-guide/classes-and-structs/fields.md) </span><span class="sxs-lookup"><span data-stu-id="8416b-141">[Fields](../../../csharp/programming-guide/classes-and-structs/fields.md) </span></span>  
 [<span data-ttu-id="8416b-142">Gewusst wie: Definieren von abstrakten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8416b-142">How to: Define Abstract Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)

