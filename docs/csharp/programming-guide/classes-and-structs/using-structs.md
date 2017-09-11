---
title: Verwenden von Strukturen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
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
ms.openlocfilehash: 67fa4f764e6e40041e4b8e37eccbd1adb2b509d3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="using-structs-c-programming-guide"></a><span data-ttu-id="08f48-102">Verwenden von Strukturen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="08f48-102">Using Structs (C# Programming Guide)</span></span>
<span data-ttu-id="08f48-103">Der `struct` -Typ eignet sich für die Darstellung von kompakten Objekten, z. B. `Point`, `Rectangle`und `Color`.</span><span class="sxs-lookup"><span data-stu-id="08f48-103">The `struct` type is suitable for representing lightweight objects such as `Point`, `Rectangle`, and `Color`.</span></span> <span data-ttu-id="08f48-104">Obwohl es ebenso einfach ist, einen Punkt als [Klasse](../../../csharp/language-reference/keywords/class.md) mit [automatisch implementierten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)darzustellen, kann eine [Struktur](../../../csharp/language-reference/keywords/struct.md) in verschiedenen Szenarien effizienter sein.</span><span class="sxs-lookup"><span data-stu-id="08f48-104">Although it is just as convenient to represent a point as a [class](../../../csharp/language-reference/keywords/class.md) with [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), a [struct](../../../csharp/language-reference/keywords/struct.md) might be more efficient in some scenarios.</span></span> <span data-ttu-id="08f48-105">Bei der Deklaration eines Arrays mit 1.000 `Point` -Objekten belegen Sie z. B. zusätzlichen Arbeitsspeicher, damit auf jedes Objekt verwiesen werden kann. In diesem Fall wäre eine Struktur weniger speicherintensiv.</span><span class="sxs-lookup"><span data-stu-id="08f48-105">For example, if you declare an array of 1000 `Point` objects, you will allocate additional memory for referencing each object; in this case, a struct would be less expensive.</span></span> <span data-ttu-id="08f48-106">Da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ein Objekt mit dem Namen <xref:System.Drawing.Point>enthält, wird die Struktur in diesem Beispiel stattdessen „CoOrds“ genannt.</span><span class="sxs-lookup"><span data-stu-id="08f48-106">Because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] contains an object called <xref:System.Drawing.Point>, the struct in this example is named "CoOrds" instead.</span></span>  
  
 <span data-ttu-id="08f48-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="08f48-107">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="08f48-108">Die Definition eines (parameterlosen) Standardkonstruktors für eine Struktur verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="08f48-108">It is an error to define a default (parameterless) constructor for a struct.</span></span> <span data-ttu-id="08f48-109">Auch durch die Initialisierung eines Instanzenfelds in einem Strukturtext wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="08f48-109">It is also an error to initialize an instance field in a struct body.</span></span> <span data-ttu-id="08f48-110">Die Strukturmember können nur mithilfe eines parametrisierten Konstruktors oder durch jeweils einzelnen Zugriff auf die Member im Anschluss an die Deklaration der Struktur initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="08f48-110">You can initialize struct members only by using a parameterized constructor or by accessing the members individually after the struct is declared.</span></span> <span data-ttu-id="08f48-111">Alle privaten oder auf andere Weise gesperrten Member können nur in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="08f48-111">Any private or otherwise inaccessible members can be initialized only in a constructor.</span></span>  
  
 <span data-ttu-id="08f48-112">Wenn Sie ein Strukturobjekt mit dem Operator [new](../../../csharp/language-reference/keywords/new.md) erzeugen, wird das Objekt erstellt und der geeignete Konstruktor aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="08f48-112">When you create a struct object using the [new](../../../csharp/language-reference/keywords/new.md) operator, it gets created and the appropriate constructor is called.</span></span> <span data-ttu-id="08f48-113">Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="08f48-113">Unlike classes, structs can be instantiated without using the `new` operator.</span></span> <span data-ttu-id="08f48-114">In einem solchen Fall gibt es keinen Konstruktoraufruf, sodass die Zuordnung effizienter ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="08f48-114">In such a case, there is no constructor call, which makes the allocation more efficient.</span></span> <span data-ttu-id="08f48-115">Die Felder werden jedoch nicht zugewiesen, und das Objekt kann erst verwendet werden, nachdem alle Felder initialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="08f48-115">However, the fields will remain unassigned and the object cannot be used until all of the fields are initialized.</span></span>  
  
 <span data-ttu-id="08f48-116">Wenn eine Struktur einen Referenztyp als Member enthält, muss der Standardkonstruktor des Members explizit aufgerufen werden. Andernfalls wird der Member nicht zugeordnet, und die Struktur kann nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08f48-116">When a struct contains a reference type as a member, the default constructor of the member must be invoked explicitly, otherwise the member remains unassigned and the struct cannot be used.</span></span> <span data-ttu-id="08f48-117">(Dies führt zu Compilerfehler CS0171.)</span><span class="sxs-lookup"><span data-stu-id="08f48-117">(This results in compiler error CS0171.)</span></span>  
  
 <span data-ttu-id="08f48-118">Bei Strukturen findet keine Vererbung wie bei Klassen statt.</span><span class="sxs-lookup"><span data-stu-id="08f48-118">There is no inheritance for structs as there is for classes.</span></span> <span data-ttu-id="08f48-119">Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="08f48-119">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="08f48-120">Stattdessen erben Strukturen von der <xref:System.Object>-Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="08f48-120">Structs, however, inherit from the base class <xref:System.Object>.</span></span> <span data-ttu-id="08f48-121">Eine Struktur kann Schnittstellen implementieren. Dies geschieht auf dieselbe Weise wie bei Klassen.</span><span class="sxs-lookup"><span data-stu-id="08f48-121">A struct can implement interfaces, and it does that exactly as classes do.</span></span>  
  
 <span data-ttu-id="08f48-122">Sie können keine Klasse mit dem `struct`-Schlüsselwort deklarieren.</span><span class="sxs-lookup"><span data-stu-id="08f48-122">You cannot declare a class using the keyword `struct`.</span></span> <span data-ttu-id="08f48-123">Klassen und Strukturen weisen in C# semantische Unterschiede auf.</span><span class="sxs-lookup"><span data-stu-id="08f48-123">In C#, classes and structs are semantically different.</span></span> <span data-ttu-id="08f48-124">Eine Struktur ist ein Werttyp, während eine Klasse ein Referenztyp ist.</span><span class="sxs-lookup"><span data-stu-id="08f48-124">A struct is a value type, while a class is a reference type.</span></span> <span data-ttu-id="08f48-125">Weitere Informationen finden Sie unter [Werttypen](../../../csharp/language-reference/keywords/value-types.md).</span><span class="sxs-lookup"><span data-stu-id="08f48-125">For more information, see [Value Types](../../../csharp/language-reference/keywords/value-types.md).</span></span>  
  
 <span data-ttu-id="08f48-126">Sofern keine Semantik für Verweistypen benötigt wird, kann das System kleine Klassen effizienter verarbeiten, wenn diese als Struktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="08f48-126">Unless you need reference-type semantics, a small class may be more efficiently handled by the system if you declare it as a struct instead.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="08f48-127">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="08f48-127">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="08f48-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08f48-128">Description</span></span>  
 <span data-ttu-id="08f48-129">In diesem Beispiel wird die `struct` -Initialisierung sowohl unter Verwendung von Standardkonstruktoren als auch unter Verwendung von parametrisierten Konstruktoren veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="08f48-129">This example demonstrates `struct` initialization using both default and parameterized constructors.</span></span>  
  
### <a name="code"></a><span data-ttu-id="08f48-130">Code</span><span class="sxs-lookup"><span data-stu-id="08f48-130">Code</span></span>  
 <span data-ttu-id="08f48-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="08f48-131">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="08f48-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="08f48-132">[!code-cs[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="08f48-133">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="08f48-133">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="08f48-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08f48-134">Description</span></span>  
 <span data-ttu-id="08f48-135">Dieses Beispiel veranschaulicht ein Feature, das ausschließlich auf Strukturen anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="08f48-135">This example demonstrates a feature that is unique to structs.</span></span> <span data-ttu-id="08f48-136">Es wird ein CoOrds-Objekt ohne Verwendung des Operators `new` erstellt.</span><span class="sxs-lookup"><span data-stu-id="08f48-136">It creates a CoOrds object without using the `new` operator.</span></span> <span data-ttu-id="08f48-137">Wenn Sie den Begriff `struct` durch `class`ersetzen, wird das Programm nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="08f48-137">If you replace the word `struct` with the word `class`, the program will not compile.</span></span>  
  
### <a name="code"></a><span data-ttu-id="08f48-138">Code</span><span class="sxs-lookup"><span data-stu-id="08f48-138">Code</span></span>  
 <span data-ttu-id="08f48-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="08f48-139">[!code-cs[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]</span></span>  
  
 <span data-ttu-id="08f48-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="08f48-140">[!code-cs[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f48-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08f48-141">See Also</span></span>  
 <span data-ttu-id="08f48-142">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="08f48-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="08f48-143">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="08f48-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="08f48-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="08f48-144">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

