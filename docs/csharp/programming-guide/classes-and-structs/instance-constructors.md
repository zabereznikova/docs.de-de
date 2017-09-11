---
title: Instanzkonstruktoren (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
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
ms.openlocfilehash: f93f622d5bf99ab7e8b1d8338192ff58472813dd
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="827a9-102">Instanzkonstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="827a9-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="827a9-103">Instanzkonstruktoren werden zum Erstellen und Initialisieren von Instanzmembervariablen verwendet, wenn Sie die Ausdruck [new](../../../csharp/language-reference/keywords/new.md) verwenden, um ein Objekt einer [Klasse](../../../csharp/language-reference/keywords/class.md) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="827a9-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="827a9-104">Sie müssen einen statischen Konstruktor definieren um eine [statische](../../../csharp/language-reference/keywords/static.md) Klasse oder eine statische Variable in einer nicht statischen Klasse zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="827a9-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="827a9-105">Weitere Informationen finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="827a9-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="827a9-106">Im folgenden Beispiel wird die Verwendung eines Instanzkonstruktors veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="827a9-106">The following example shows an instance constructor:</span></span>  
  
 <span data-ttu-id="827a9-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-107">[!code-cs[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="827a9-108">Der Deutlichkeit halber enthält diese Klasse öffentliche Felder.</span><span class="sxs-lookup"><span data-stu-id="827a9-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="827a9-109">Das Verwenden von öffentlichen Felder wird beim Programmieren nicht empfohlen, da so jede Methode im Programm uneingeschränkten und ungeprüften Zugriff auf das Innenleben eines Objekts erhält.</span><span class="sxs-lookup"><span data-stu-id="827a9-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="827a9-110">Datenmember sollten im Allgemeinen privat sein. Außerdem sollte auf sie nur über Klassenmethoden und Eigenschaften zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="827a9-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="827a9-111">Dieser Instanzkonstruktor wird aufgerufen, wenn ein Objekt basierend auf der `CoOrds`-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="827a9-111">This instance constructor is called whenever an object based on the `CoOrds` class is created.</span></span> <span data-ttu-id="827a9-112">Ein derartiger Konstruktor, der keine Argumente akzeptiert, wird als *Standardkonstruktor* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="827a9-112">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="827a9-113">Es kann jedoch oft hilfreich sein, weitere Konstruktoren bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="827a9-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="827a9-114">Sie können beispielsweise einen Konstruktor in die `CoOrds`-Klasse einfügen, mit dem Sie die Anfangswerte der Datenmember angeben können:</span><span class="sxs-lookup"><span data-stu-id="827a9-114">For example, we can add a constructor to the `CoOrds` class that allows us to specify the initial values for the data members:</span></span>  
  
 <span data-ttu-id="827a9-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-115">[!code-cs[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="827a9-116">Damit können `CoOrd`-Objekte mit Standard- oder spezifischen Anfangswerten erstellt werden. Dies geschieht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="827a9-116">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 <span data-ttu-id="827a9-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-117">[!code-cs[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="827a9-118">Wenn eine Klasse über keinen Konstruktor verfügt, wird automatisch ein Standardkonstruktor generiert, und die Objektfelder werden mit Standardwerte initialisiert.</span><span class="sxs-lookup"><span data-stu-id="827a9-118">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="827a9-119">Ein [int](../../../csharp/language-reference/keywords/int.md)-Objekt wird beispielsweise auf 0 (null) initialisiert.</span><span class="sxs-lookup"><span data-stu-id="827a9-119">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="827a9-120">Weitere Informationen zu Standardwerten finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="827a9-120">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="827a9-121">Da der Standardkonstruktor der `CoOrds`-Klasse alle Datenmember auf 0 (null) initialisiert, kann er komplett entfernt werden, ohne dass die Arbeitsweise der Klasse geändert wird.</span><span class="sxs-lookup"><span data-stu-id="827a9-121">Therefore, because the `CoOrds` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="827a9-122">Unter Beispiel 1 weiter unten in diesem Thema finden Sie ein vollständiges Beispiel mit mehreren Konstruktoren. Unter Beispiel 2 finden Sie ein Beispiel für einen automatisch generierten Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="827a9-122">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="827a9-123">Instanzkonstruktoren können ebenfalls dazu verwendet werden, die Instanzkonstruktoren von Basisklassen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="827a9-123">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="827a9-124">Der Klassenkonstruktor kann den Konstruktor der Basisklasse mit dem Initialisierer wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="827a9-124">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 <span data-ttu-id="827a9-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-125">[!code-cs[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="827a9-126">In diesem Beispiel übergibt die `Circle`-Klasse die Werte des Radius und der Höhe an den Konstruktor, der von `Shape` bereitgestellt wird, von dem `Circle` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="827a9-126">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="827a9-127">Unter Beispiel 3 in diesem Thema finden Sie ein vollständiges Beispiel mit `Shape` und `Circle`.</span><span class="sxs-lookup"><span data-stu-id="827a9-127">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="827a9-128">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="827a9-128">Example 1</span></span>  
 <span data-ttu-id="827a9-129">Das folgende Beispiel veranschaulicht eine Klasse mit zwei Klassenkonstruktoren. Einer der Konstruktoren hat kein Argument und der andere verfügt über zwei.</span><span class="sxs-lookup"><span data-stu-id="827a9-129">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 <span data-ttu-id="827a9-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-130">[!code-cs[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="827a9-131">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="827a9-131">Example 2</span></span>  
 <span data-ttu-id="827a9-132">In diesem Beispiel hat die `Person`-Klasse keine Konstruktoren. In einem solchen Fall wird automatisch ein Standardkonstruktor bereitgestellt, und die Felder werden auf ihre Standardwerte initialisiert.</span><span class="sxs-lookup"><span data-stu-id="827a9-132">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 <span data-ttu-id="827a9-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-133">[!code-cs[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="827a9-134">Beachten Sie, dass der Standardwert von `age` `0` ist, und der Standardwert von `name` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="827a9-134">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="827a9-135">Weitere Informationen zu Standardwerten finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="827a9-135">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="827a9-136">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="827a9-136">Example 3</span></span>  
 <span data-ttu-id="827a9-137">Im folgenden Beispiel wird die Verwendung vom Basisklasseninitialisierer veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="827a9-137">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="827a9-138">Die `Circle`-Klasse wird von der allgemeinen Klasse `Shape` abgeleitet, und die `Cylinder`-Klasse wird von der `Circle`-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="827a9-138">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="827a9-139">Der Konstruktor von jeder abgeleiteten Klasse verwendet deren Basisklasseninitialisierer.</span><span class="sxs-lookup"><span data-stu-id="827a9-139">The constructor on each derived class is using its base class initializer.</span></span>  
  
 <span data-ttu-id="827a9-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="827a9-140">[!code-cs[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="827a9-141">Weitere Beispiele für das Aufrufen des Basisklassenkonstruktors finden Sie unter [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) und [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="827a9-141">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827a9-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="827a9-142">See Also</span></span>  
 <span data-ttu-id="827a9-143">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="827a9-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="827a9-144">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="827a9-144">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="827a9-145">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="827a9-145">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="827a9-146">[Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="827a9-146">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 [<span data-ttu-id="827a9-147">static</span><span class="sxs-lookup"><span data-stu-id="827a9-147">static</span></span>](../../../csharp/language-reference/keywords/static.md)

