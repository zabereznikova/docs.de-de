---
title: Instanzkonstruktoren – C#-Programmierhandbuch
description: Instanzkonstruktoren in C# erstellen und initialisieren Instanzmembervariablen, wenn Sie den neuen Ausdruck verwenden, um ein Objekt einer Klasse zu erstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: f1845601f2a0237206d05e3cc3cbbca68492020c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186132"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="130ca-103">Instanzkonstruktoren (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="130ca-103">Instance Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="130ca-104">Instanzkonstruktoren werden zum Erstellen und Initialisieren von Instanzmembervariablen verwendet, wenn Sie die Ausdruck [new](../../language-reference/operators/new-operator.md) verwenden, um ein Objekt einer [Klasse](../../language-reference/keywords/class.md) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="130ca-104">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../language-reference/operators/new-operator.md) expression to create an object of a [class](../../language-reference/keywords/class.md).</span></span> <span data-ttu-id="130ca-105">Sie müssen einen statischen Konstruktor definieren um eine [statische](../../language-reference/keywords/static.md) Klasse oder eine statische Variable in einer nicht statischen Klasse zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="130ca-105">To initialize a [static](../../language-reference/keywords/static.md) class, or static variables in a non-static class, you define a static constructor.</span></span> <span data-ttu-id="130ca-106">Weitere Informationen finden Sie unter [Statische Konstruktoren](./static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="130ca-106">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
 <span data-ttu-id="130ca-107">Im folgenden Beispiel wird die Verwendung eines Instanzkonstruktors veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="130ca-107">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> <span data-ttu-id="130ca-108">Der Deutlichkeit halber enthält diese Klasse öffentliche Felder.</span><span class="sxs-lookup"><span data-stu-id="130ca-108">For clarity, this class contains public fields.</span></span> <span data-ttu-id="130ca-109">Das Verwenden von öffentlichen Felder wird beim Programmieren nicht empfohlen, da so jede Methode im Programm uneingeschränkten und ungeprüften Zugriff auf das Innenleben eines Objekts erhält.</span><span class="sxs-lookup"><span data-stu-id="130ca-109">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="130ca-110">Datenmember sollten im Allgemeinen privat sein. Außerdem sollte auf sie nur über Klassenmethoden und Eigenschaften zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="130ca-110">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="130ca-111">Dieser Instanzkonstruktor wird aufgerufen, wenn ein Objekt basierend auf der `Coords`-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="130ca-111">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="130ca-112">Ein derartiger Konstruktor, der keine Argumente akzeptiert, wird als *parameterloser Konstruktor* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="130ca-112">A constructor like this one, which takes no arguments, is called a *parameterless constructor*.</span></span> <span data-ttu-id="130ca-113">Es kann jedoch oft hilfreich sein, weitere Konstruktoren bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="130ca-113">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="130ca-114">Sie können beispielsweise einen Konstruktor in die `Coords`-Klasse einfügen, mit dem Sie die Anfangswerte der Datenmember angeben können:</span><span class="sxs-lookup"><span data-stu-id="130ca-114">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 <span data-ttu-id="130ca-115">Damit können `Coords`-Objekte mit Standard- oder spezifischen Anfangswerten erstellt werden. Dies geschieht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="130ca-115">This allows `Coords` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 <span data-ttu-id="130ca-116">Wenn eine Klasse über keinen Konstruktor verfügt, wird automatisch ein parameterloser Konstruktor generiert, und die Objektfelder werden mit Standardwerte initialisiert.</span><span class="sxs-lookup"><span data-stu-id="130ca-116">If a class does not have a constructor, a parameterless constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="130ca-117">Ein [int](../../language-reference/builtin-types/integral-numeric-types.md)-Objekt wird beispielsweise auf 0 (null) initialisiert.</span><span class="sxs-lookup"><span data-stu-id="130ca-117">For example, an [int](../../language-reference/builtin-types/integral-numeric-types.md) is initialized to 0.</span></span> <span data-ttu-id="130ca-118">Informationen zu den Typstandardwerten finden Sie unter [Standardwerte der C#-Typen](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="130ca-118">For information about the type default values, see [Default values of C# types](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="130ca-119">Da der parameterloser Konstruktor der `Coords`-Klasse alle Datenmember auf 0 (null) initialisiert, kann er komplett entfernt werden, ohne dass die Arbeitsweise der Klasse geändert wird.</span><span class="sxs-lookup"><span data-stu-id="130ca-119">Therefore, because the `Coords` class parameterless constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="130ca-120">Unter Beispiel 1 weiter unten in diesem Thema finden Sie ein vollständiges Beispiel mit mehreren Konstruktoren. Unter Beispiel 2 finden Sie ein Beispiel für einen automatisch generierten Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="130ca-120">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="130ca-121">Instanzkonstruktoren können ebenfalls dazu verwendet werden, die Instanzkonstruktoren von Basisklassen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="130ca-121">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="130ca-122">Der Klassenkonstruktor kann den Konstruktor der Basisklasse mit dem Initialisierer wie folgt aufrufen:</span><span class="sxs-lookup"><span data-stu-id="130ca-122">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 <span data-ttu-id="130ca-123">In diesem Beispiel übergibt die `Circle`-Klasse die Werte des Radius und der Höhe an den Konstruktor, der von `Shape` bereitgestellt wird, von dem `Circle` abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="130ca-123">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="130ca-124">Unter Beispiel 3 in diesem Thema finden Sie ein vollständiges Beispiel mit `Shape` und `Circle`.</span><span class="sxs-lookup"><span data-stu-id="130ca-124">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="130ca-125">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="130ca-125">Example 1</span></span>  

 <span data-ttu-id="130ca-126">Das folgende Beispiel veranschaulicht eine Klasse mit zwei Klassenkonstruktoren. Einer der Konstruktoren hat kein Argument und der andere verfügt über zwei.</span><span class="sxs-lookup"><span data-stu-id="130ca-126">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a><span data-ttu-id="130ca-127">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="130ca-127">Example 2</span></span>  

 <span data-ttu-id="130ca-128">In diesem Beispiel hat die `Person`-Klasse keine Konstruktoren. In einem solchen Fall wird automatisch ein parameterloser Konstruktor bereitgestellt, und die Felder werden auf ihre Standardwerte initialisiert.</span><span class="sxs-lookup"><span data-stu-id="130ca-128">In this example, the class `Person` does not have any constructors, in which case, a parameterless constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 <span data-ttu-id="130ca-129">Beachten Sie, dass der Standardwert von `age``0` ist, und der Standardwert von `name` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="130ca-129">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="130ca-130">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="130ca-130">Example 3</span></span>  

 <span data-ttu-id="130ca-131">Im folgenden Beispiel wird die Verwendung vom Basisklasseninitialisierer veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="130ca-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="130ca-132">Die `Circle`-Klasse wird von der allgemeinen Klasse `Shape` abgeleitet, und die `Cylinder`-Klasse wird von der `Circle`-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="130ca-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="130ca-133">Der Konstruktor von jeder abgeleiteten Klasse verwendet deren Basisklasseninitialisierer.</span><span class="sxs-lookup"><span data-stu-id="130ca-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 <span data-ttu-id="130ca-134">Weitere Beispiele für das Aufrufen des Basisklassenkonstruktors finden Sie unter [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) und [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="130ca-134">For more examples on invoking the base class constructors, see [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md), and [base](../../language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130ca-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="130ca-135">See also</span></span>

- [<span data-ttu-id="130ca-136">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="130ca-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="130ca-137">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="130ca-137">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="130ca-138">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="130ca-138">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="130ca-139">Finalizer</span><span class="sxs-lookup"><span data-stu-id="130ca-139">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="130ca-140">static</span><span class="sxs-lookup"><span data-stu-id="130ca-140">static</span></span>](../../language-reference/keywords/static.md)
