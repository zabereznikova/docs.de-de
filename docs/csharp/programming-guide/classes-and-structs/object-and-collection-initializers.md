---
title: Objekt- und Auflistungsinitialisierer – C#-Programmierhandbuch
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 5565f37c9cfd8cb84c07f9ecc6f6c2edf8c66c61
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714752"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="9039c-102">Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9039c-102">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="9039c-103">Mit C# können Sie ein Objekt oder eine Sammlung instanziieren und Memberzuweisungen in einer einzigen Anweisung durchführen.</span><span class="sxs-lookup"><span data-stu-id="9039c-103">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="9039c-104">Objektinitialisierer</span><span class="sxs-lookup"><span data-stu-id="9039c-104">Object initializers</span></span>

<span data-ttu-id="9039c-105">Mit Objektinitialisierern können Sie allen verfügbaren Feldern oder Eigenschaften eines Objekts zum Erstellungszeitpunkt Werte zuweisen, ohne einen Konstruktor gefolgt von Zeilen mit Zuweisungsanweisungen aufrufen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="9039c-105">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="9039c-106">Mit der Objektinitialisierersyntax können Sie Argumente für einen Konstruktor angeben oder die Argumente (und Klammersyntax) weglassen.</span><span class="sxs-lookup"><span data-stu-id="9039c-106">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="9039c-107">Das folgende Beispiel zeigt, wie Sie einen Objektinitialisierer mit einem benannten Typ (`Cat`) verwenden und den parameterlosen Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9039c-107">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="9039c-108">Beachten Sie die Verwendung automatisch implementierter Eigenschaften in der `Cat`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9039c-108">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="9039c-109">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9039c-109">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
<span data-ttu-id="9039c-110">Die Syntax von Objektinitialisierern ermöglicht Ihnen die Erstellung einer Instanz und weist danach das neu erstellte Objekt mit seinen zugewiesenen Eigenschaften der Variable in der Zuweisung zu.</span><span class="sxs-lookup"><span data-stu-id="9039c-110">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="9039c-111">Ab C# 6 können die Objektinitialisierer nicht nur Felder und Eigenschaften zuweisen, sondern auch zusätzlich Indexer festlegen.</span><span class="sxs-lookup"><span data-stu-id="9039c-111">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="9039c-112">Betrachten Sie diese grundlegende `Matrix`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="9039c-112">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="9039c-113">Sie können die Identitätsmatrix mit folgendem Code initialisieren:</span><span class="sxs-lookup"><span data-stu-id="9039c-113">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="9039c-114">Alle zugänglichen Indexer, die zugängliche Setter enthalten, können unabhängig von der Anzahl und Typen der Argumente als einer der Ausdrücke in einem Objektinitialisierer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9039c-114">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="9039c-115">Die Indexargumente bilden die linke Seite der Zuweisung, und der Wert befindet sich auf der rechten Seite des Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="9039c-115">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="9039c-116">Diese sind beispielsweise alle gültig, wenn `IndexersExample` über die entsprechenden Indexer verfügt:</span><span class="sxs-lookup"><span data-stu-id="9039c-116">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="9039c-117">Der `IndexersExample`-Typ muss für das Erstellen des obigen Codes die folgenden Member vorweisen:</span><span class="sxs-lookup"><span data-stu-id="9039c-117">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="9039c-118">Objektinitialisierer mit anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="9039c-118">Object Initializers with anonymous types</span></span>

<span data-ttu-id="9039c-119">Obwohl Objektinitialisierer in jedem Kontext verwendet werden können, sind sie vor allem in LINQ-Abfrageausdrücken nützlich.</span><span class="sxs-lookup"><span data-stu-id="9039c-119">Although object initializers can be used in any context, they are especially useful in LINQ query expressions.</span></span> <span data-ttu-id="9039c-120">Abfrageausdrücke verwenden häufig [anonyme Typen](./anonymous-types.md), die nur mit einem Objektinitialisierer initialisiert werden können, wie in der folgenden Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9039c-120">Query expressions make frequent use of [anonymous types](./anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="9039c-121">Anonyme Typen ermöglichen der `select`-Klausel in einem LINQ-Abfrageausdruck, Objekte der ursprünglichen Sequenz in Objekte zu transformieren, deren Wert und Form sich vom Original unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="9039c-121">Anonymous types enable the `select` clause in a LINQ query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="9039c-122">Dies ist nützlich, wenn Sie nur einen Teil der Informationen aus jedem Objekt in einer Sequenz speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="9039c-122">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="9039c-123">Im folgenden Beispiel wird angenommen, dass ein Produktobjekt (`p`) viele Felder und Methoden enthält und dass Sie nur eine Sequenz von Objekten erstellen möchten, die den Produktnamen und den Einzelpreis enthalten.</span><span class="sxs-lookup"><span data-stu-id="9039c-123">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="9039c-124">Wenn diese Abfrage ausgeführt wird, enthält die `productInfos`-Variable eine Sequenz von Objekten, auf die Sie über eine `foreach`-Anweisung, wie im folgenden Beispiel gezeigt, zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="9039c-124">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="9039c-125">Jedes Objekt im neuen anonymen Typ weist zwei öffentliche Eigenschaften auf, die die gleichen Namen wie die Eigenschaften oder Felder im ursprünglichen Objekt erhalten.</span><span class="sxs-lookup"><span data-stu-id="9039c-125">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="9039c-126">Sie können ein Feld auch umbenennen, wenn Sie einen anonymen Typ erstellen. Im folgenden Beispiel wird das `UnitPrice`-Feld in `Price` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="9039c-126">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="9039c-127">Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="9039c-127">Collection initializers</span></span>

<span data-ttu-id="9039c-128">Mit Auflistungsinitialisierern können Sie einen oder mehrere Elementinitialisierer festlegen, wenn Sie einen Auflistungstyp initialisieren, der <xref:System.Collections.IEnumerable> implementiert und über `Add` mit der entsprechenden Signatur als Instanzmethode oder Erweiterungsmethode verfügt.</span><span class="sxs-lookup"><span data-stu-id="9039c-128">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="9039c-129">Die Elementinitialisierer können ein einfacher Wert, ein Ausdruck oder ein Objektinitialisierer sein.</span><span class="sxs-lookup"><span data-stu-id="9039c-129">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="9039c-130">Wenn Sie einen Sammlungsinitialisierer verwenden, ist es nicht nötig, selbst Aufrufe anzugeben, da der Compiler diese automatisch hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="9039c-130">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="9039c-131">Im folgenden Beispiel werden zwei einfache Sammlungsinitialisierer dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9039c-131">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="9039c-132">Der folgende Auflistungsinitialisierer verwendet Objektinitialisierer, um Objekte der `Cat`-Klasse, die in einem vorherigen Beispiel definiert wurden, zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9039c-132">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="9039c-133">Beachten Sie, dass die einzelnen Objektinitialisierer in geschweifte Klammern eingeschlossen und durch Kommas voneinander getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="9039c-133">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="9039c-134">Sie können [NULL](../../language-reference/keywords/null.md) als ein Element in einem Auflistungsinitialisierer festlegen, wenn die `Add`-Methode der Auflistung dies zulässt.</span><span class="sxs-lookup"><span data-stu-id="9039c-134">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="9039c-135">Sie können indizierte Elemente angeben, wenn die Sammlung das Lesen oder Schreiben von Indizierungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9039c-135">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="9039c-136">Im vorherigen Beispiel wurde Code generiert, der die <xref:System.Collections.Generic.Dictionary%602.Item(%600)>-Eigenschaft zum Festlegen der Werte aufruft.</span><span class="sxs-lookup"><span data-stu-id="9039c-136">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="9039c-137">Mit Versionen vor C# 6 können Sie Wörterbücher und andere assoziative Container mithilfe der folgenden Syntax initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9039c-137">Before C# 6, you could initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="9039c-138">Es gilt zu beachten, dass anstelle einer Indexersyntax mit Klammern und einer Zuweisung ein Objekt mit mehreren Werten verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="9039c-138">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="9039c-139">Bei diesem Beispiel eines Initialisierers wird <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> aufgerufen, um die drei Elemente dem Wörterbuch hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9039c-139">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="9039c-140">Diese zwei verschiedenen Arten des Initialisierens assoziativer Sammlungen verhalten sich aufgrund der vom Compiler generierten Methodenaufrufe etwas unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="9039c-140">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="9039c-141">Beide Varianten unterstützen aber die `Dictionary`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9039c-141">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="9039c-142">Bei anderen Typen wird abhängig von deren öffentlicher API möglicherweise nur eine der beiden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9039c-142">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="9039c-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9039c-143">Examples</span></span>

<span data-ttu-id="9039c-144">Im folgenden Beispiel werden die Konzepte des Objekt- und Auflistungsinitialisierers verbunden.</span><span class="sxs-lookup"><span data-stu-id="9039c-144">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="9039c-145">Im folgenden Beispiel wird ein Objekt veranschaulicht, das <xref:System.Collections.IEnumerable> implementiert und eine `Add`-Methode mit mehreren Parametern enthält. Es wird ein Sammlungsinitialisierer mit mehreren Elementen pro Element in der Liste verwendet, die der Signatur der `Add`-Methode entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9039c-145">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="9039c-146">`Add`-Methoden können durch das Schlüsselwort `params` eine variable Anzahl von Argumenten akzeptieren, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9039c-146">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="9039c-147">In diesem Beispiel wird die benutzerdefinierte Implementierung eines Indexers sowie die Initialisierung einer Sammlung mithilfe von Indizes veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9039c-147">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="9039c-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9039c-148">See also</span></span>

- [<span data-ttu-id="9039c-149">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9039c-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9039c-150">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="9039c-150">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="9039c-151">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="9039c-151">Anonymous Types</span></span>](anonymous-types.md)
