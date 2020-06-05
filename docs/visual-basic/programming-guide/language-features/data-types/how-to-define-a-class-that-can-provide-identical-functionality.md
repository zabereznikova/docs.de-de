---
title: 'Vorgehensweise: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann'
ms.date: 07/20/2015
helpviewer_keywords:
- data type arguments [Visual Basic], using
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- data type parameters [Visual Basic], using
- generics [Visual Basic], defining classes with type parameters
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- type arguments
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
- parameters [Visual Basic], data type
- generics [Visual Basic], defining generic types
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: a914adf8-e68f-4819-a6b1-200d1cf1c21c
ms.openlocfilehash: 3b1f47250453c32735d633b98da0bd0ddb1ed5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393856"
---
# <a name="how-to-define-a-class-that-can-provide-identical-functionality-on-different-data-types-visual-basic"></a><span data-ttu-id="02a74-102">Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02a74-102">How to: Define a Class That Can Provide Identical Functionality on Different Data Types (Visual Basic)</span></span>
<span data-ttu-id="02a74-103">Sie können eine Klasse definieren, über die Sie Objekte erstellen können, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="02a74-103">You can define a class from which you can create objects that provide identical functionality on different data types.</span></span> <span data-ttu-id="02a74-104">Hierzu geben Sie in der Definition mindestens einen *Typparameter* an.</span><span class="sxs-lookup"><span data-stu-id="02a74-104">To do this, you specify one or more *type parameters* in the definition.</span></span> <span data-ttu-id="02a74-105">Die Klasse kann dann als Vorlage für Objekte fungieren, für die verschiedene Datentypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02a74-105">The class can then serve as a template for objects that use various data types.</span></span> <span data-ttu-id="02a74-106">Eine in dieser Weise definierte Klasse wird als *generische Klasse*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="02a74-106">A class defined in this way is called a *generic class*.</span></span>  
  
 <span data-ttu-id="02a74-107">Der Vorteil des Definierens einer generischen Klasse besteht darin, dass Sie die Klasse nur einmal definieren müssen und diese in Ihrem Code verwenden können, um viele Objekte zu erstellen, für die unterschiedliche Datentypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02a74-107">The advantage of defining a generic class is that you define it just once, and your code can use it to create many objects that use a wide variety of data types.</span></span> <span data-ttu-id="02a74-108">Dies führt zu einer besseren Leistung, als dies der Fall ist, wenn die Klasse mit dem `Object` -Typ definiert wird.</span><span class="sxs-lookup"><span data-stu-id="02a74-108">This results in better performance than defining the class with the `Object` type.</span></span>  
  
 <span data-ttu-id="02a74-109">Zusätzlich zu generischen Klassen können Sie auch generische Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="02a74-109">In addition to classes, you can also define and use generic structures, interfaces, procedures, and delegates.</span></span>  
  
### <a name="to-define-a-class-with-a-type-parameter"></a><span data-ttu-id="02a74-110">So definieren Sie eine Klasse mit einem Typparameter</span><span class="sxs-lookup"><span data-stu-id="02a74-110">To define a class with a type parameter</span></span>  
  
1. <span data-ttu-id="02a74-111">Definieren Sie die Klasse auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="02a74-111">Define the class in the normal way.</span></span>  
  
2. <span data-ttu-id="02a74-112">Fügen Sie `(Of` *typeparameter* `)` unmittelbar nach dem Klassennamen hinzu, um einen Typparameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02a74-112">Add `(Of` *typeparameter*`)` immediately after the class name to specify a type parameter.</span></span>  
  
3. <span data-ttu-id="02a74-113">Sind mehrere Typparameter vorhanden, erstellen Sie innerhalb der Klammern eine Liste mit Kommas als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="02a74-113">If you have more than one type parameter, make a comma-separated list inside the parentheses.</span></span> <span data-ttu-id="02a74-114">Geben Sie das `Of` -Schlüsselwort nur einmal an.</span><span class="sxs-lookup"><span data-stu-id="02a74-114">Do not repeat the `Of` keyword.</span></span>  
  
4. <span data-ttu-id="02a74-115">Werden im Code Operationen für einen Typparameter ausgeführt, die über eine einfache Zuweisung hinausgehen, geben Sie nach dem Typparameter eine `As` -Klausel an, um die entsprechende Anzahl von *Einschränkungen*hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="02a74-115">If your code performs operations on a type parameter other than simple assignment, follow that type parameter with an `As` clause to add one or more *constraints*.</span></span> <span data-ttu-id="02a74-116">Eine Einschränkung gewährleistet, dass der für den Typparameter angegebene Typ eine Anforderung erfüllt, beispielsweise eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="02a74-116">A constraint guarantees that the type supplied for that type parameter satisfies a requirement such as the following:</span></span>  
  
    - <span data-ttu-id="02a74-117">Unterstützt eine Operation, etwa `>`, die der Code ausführt</span><span class="sxs-lookup"><span data-stu-id="02a74-117">Supports an operation, such as `>`, that your code performs</span></span>  
  
    - <span data-ttu-id="02a74-118">Unterstützt einen Member, etwa eine Methode, auf den der Code zugreift</span><span class="sxs-lookup"><span data-stu-id="02a74-118">Supports a member, such as a method, that your code accesses</span></span>  
  
    - <span data-ttu-id="02a74-119">Macht einen parameterlosen Konstruktor verfügbar</span><span class="sxs-lookup"><span data-stu-id="02a74-119">Exposes a parameterless constructor</span></span>  
  
     <span data-ttu-id="02a74-120">Wenn Sie keine Einschränkungen angeben, können im Code nur Operationen und Member verwendet werden, die vom [Object Data Type](../../../language-reference/data-types/object-data-type.md)unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="02a74-120">If you do not specify any constraints, the only operations and members your code can use are those supported by the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="02a74-121">Weitere Informationen finden Sie unter [Type List](../../../language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="02a74-121">For more information, see [Type List](../../../language-reference/statements/type-list.md).</span></span>  
  
5. <span data-ttu-id="02a74-122">Identifizieren Sie jeden Klassenmember, der mit einem bereitgestellten Typ deklariert werden soll, und deklarieren Sie ihn `As` `typeparameter` .</span><span class="sxs-lookup"><span data-stu-id="02a74-122">Identify every class member that is to be declared with a supplied type, and declare it `As` `typeparameter`.</span></span> <span data-ttu-id="02a74-123">Dies gilt für die interne Speicherung, für Prozedurparameter und für Rückgabewerte.</span><span class="sxs-lookup"><span data-stu-id="02a74-123">This applies to internal storage, procedure parameters, and return values.</span></span>  
  
6. <span data-ttu-id="02a74-124">Im Code dürfen nur Operationen und Methoden verwenden, die von jedem Datentyp unterstützt werden, der im Code für `itemType`angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="02a74-124">Be sure your code uses only operations and methods that are supported by any data type it can supply to `itemType`.</span></span>  
  
     <span data-ttu-id="02a74-125">Im folgenden Beispiel wird eine Klasse definiert, in der eine sehr einfache Liste verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="02a74-125">The following example defines a class that manages a very simple list.</span></span> <span data-ttu-id="02a74-126">Die Klasse speichert die Liste im internen Array `items`, und der verwendende Code kann den Datentyp der Listenelemente deklarieren.</span><span class="sxs-lookup"><span data-stu-id="02a74-126">It holds the list in the internal array `items`, and the using code can declare the data type of the list elements.</span></span> <span data-ttu-id="02a74-127">Mit einem parametrisierten Konstruktor kann der Using-Code die obere Grenze von festlegen `items` , und der Parameter lose Konstruktor legt diese auf 9 (für insgesamt 10 Elemente) fest.</span><span class="sxs-lookup"><span data-stu-id="02a74-127">A parameterized constructor allows the using code to set the upper bound of `items`, and the parameterless constructor sets this to 9 (for a total of 10 items).</span></span>  
  
     [!code-vb[VbVbalrDataTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#7)]  
  
     <span data-ttu-id="02a74-128">Sie können eine Klasse aus `simpleList` deklarieren, die eine Liste von `Integer` -Werten enthält, eine andere Klasse, die eine Liste von `String` -Werten enthält, und eine weitere Klasse, die `Date` -Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="02a74-128">You can declare a class from `simpleList` to hold a list of `Integer` values, another class to hold a list of `String` values, and another to hold `Date` values.</span></span> <span data-ttu-id="02a74-129">Abgesehen vom Datentyp der Listenmember verhalten sich Objekte, die aus einer dieser Klassen erstellt wurden, gleich.</span><span class="sxs-lookup"><span data-stu-id="02a74-129">Except for the data type of the list members, objects created from all these classes behave identically.</span></span>  
  
     <span data-ttu-id="02a74-130">Das Typargument, das im verwendenden Code für `itemType` bereitgestellt wird, kann ein systeminterner Typ, etwa `Boolean` oder `Double`, eine Struktur, eine Enumeration oder ein beliebiger Klassentyp sein, einschließlich eines in der Anwendung definierten Klassentyps.</span><span class="sxs-lookup"><span data-stu-id="02a74-130">The type argument that the using code supplies to `itemType` can be an intrinsic type such as `Boolean` or `Double`, a structure, an enumeration, or any type of class, including one that your application defines.</span></span>  
  
     <span data-ttu-id="02a74-131">Sie können die Klasse `simpleList` mit dem folgenden Code testen.</span><span class="sxs-lookup"><span data-stu-id="02a74-131">You can test the class `simpleList` with the following code.</span></span>  
  
     [!code-vb[VbVbalrDataTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="02a74-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02a74-132">See also</span></span>

- [<span data-ttu-id="02a74-133">Datentypen</span><span class="sxs-lookup"><span data-stu-id="02a74-133">Data Types</span></span>](index.md)
- [<span data-ttu-id="02a74-134">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02a74-134">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="02a74-135">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="02a74-135">Language Independence and Language-Independent Components</span></span>](../../../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="02a74-136">Natürlich</span><span class="sxs-lookup"><span data-stu-id="02a74-136">Of</span></span>](../../../language-reference/statements/of-clause.md)
- [<span data-ttu-id="02a74-137">Type List</span><span class="sxs-lookup"><span data-stu-id="02a74-137">Type List</span></span>](../../../language-reference/statements/type-list.md)
- [<span data-ttu-id="02a74-138">Vorgehensweise: Verwenden einer generischen Klasse</span><span class="sxs-lookup"><span data-stu-id="02a74-138">How to: Use a Generic Class</span></span>](how-to-use-a-generic-class.md)
- [<span data-ttu-id="02a74-139">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="02a74-139">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
