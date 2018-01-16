---
title: Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 628f08aaebfa209fc9cb7cfb2b506fc67d5424f9
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="c7364-102">Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c7364-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="c7364-103">Mit Objektinitialisierern können Sie allen verfügbaren Feldern oder Eigenschaften eines Objekts zum Erstellungszeitpunkt Werte zuweisen, ohne einen Konstruktor gefolgt von Zeilen mit Zuweisungsanweisungen aufrufen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c7364-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="c7364-104">Mit der Objektinitialisierersyntax können Sie Argumente für einen Konstruktor angeben oder die Argumente (und Klammersyntax) weglassen.</span><span class="sxs-lookup"><span data-stu-id="c7364-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="c7364-105">Im folgenden Beispiel werden die Verwendung eines Objektinitialisierers mit einem benannten Typ, `Cat`, und das Aufrufen des Standardkonstruktors veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c7364-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="c7364-106">Beachten Sie die Verwendung automatisch implementierter Eigenschaften in der `Cat`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c7364-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="c7364-107">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c7364-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="c7364-108">Die Syntax von Objektinitialisierern ermöglicht Ihnen die Erstellung einer Instanz und weist danach das neu erstellte Objekt mit seinen zugewiesenen Eigenschaften der Variable in der Zuweisung zu.</span><span class="sxs-lookup"><span data-stu-id="c7364-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="c7364-109">Objektinitialisierer mit anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="c7364-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="c7364-110">Obwohl Objektinitialisierer in jedem Kontext verwendet werden können, sind sie vor allem in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücken nützlich.</span><span class="sxs-lookup"><span data-stu-id="c7364-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="c7364-111">Abfrageausdrücke verwenden häufig [anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), die nur mit einem Objektinitialisierer initialisiert werden können, wie in der folgenden Deklaration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c7364-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="c7364-112">Anonyme Typen ermöglichen der `select`-Klausel in einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck, Objekte der ursprünglichen Sequenz in Objekte zu transformieren, deren Wert und Form sich vom Original unterscheiden können.</span><span class="sxs-lookup"><span data-stu-id="c7364-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="c7364-113">Dies ist nützlich, wenn Sie nur einen Teil der Informationen aus jedem Objekt in einer Sequenz speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="c7364-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="c7364-114">Im folgenden Beispiel wird angenommen, dass ein Produktobjekt (`p`) viele Felder und Methoden enthält und dass Sie nur eine Sequenz von Objekten erstellen möchten, die den Produktnamen und den Einzelpreis enthalten.</span><span class="sxs-lookup"><span data-stu-id="c7364-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="c7364-115">Wenn diese Abfrage ausgeführt wird, enthält die `productInfos`-Variable eine Sequenz von Objekten, auf die Sie über eine `foreach`-Anweisung, wie im folgenden Beispiel gezeigt, zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="c7364-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="c7364-116">Jedes Objekt im neuen anonymen Typ hat zwei öffentliche Eigenschaften, die die gleichen Namen wie die Eigenschaften oder Felder im ursprünglichen Objekt erhalten.</span><span class="sxs-lookup"><span data-stu-id="c7364-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="c7364-117">Sie können ein Feld auch umbenennen, wenn Sie einen anonymen Typ erstellen. Im folgenden Beispiel wird das `UnitPrice`-Feld in `Price` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="c7364-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="c7364-118">Objektinitialisierer mit dem Typ, der NULL-Werte zulässt</span><span class="sxs-lookup"><span data-stu-id="c7364-118">Object initializers with nullable types</span></span>  
 <span data-ttu-id="c7364-119">Die Verwendung eines Objektinitialisierers mit einer Struktur, die NULL-Werte zulässt, ist ein Fehler, der zum Zeitpunkt der Kompilierung auftritt.</span><span class="sxs-lookup"><span data-stu-id="c7364-119">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="c7364-120">Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="c7364-120">Collection initializers</span></span>  
 <span data-ttu-id="c7364-121">Mit Auflistungsinitialisierern können Sie einen oder mehrere Elementinitialisierer festlegen, wenn Sie einen Auflistungstyp initialisieren, der <xref:System.Collections.IEnumerable> implementiert und über `Add` mit der entsprechenden Signatur als Instanzmethode oder Erweiterungsmethode verfügt.</span><span class="sxs-lookup"><span data-stu-id="c7364-121">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="c7364-122">Die Elementinitialisierer können ein einfacher Wert, ein Ausdruck oder ein Objektinitialisierer sein.</span><span class="sxs-lookup"><span data-stu-id="c7364-122">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="c7364-123">Durch den Einsatz eines Auflistungsinitialisierers müssen Sie nicht mehrere Aufrufe der `Add`-Methode für die Klasse in Ihrem Quellcode angeben; der Compiler fügt die Aufrufe hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7364-123">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="c7364-124">In den folgenden Beispielen werden zwei einfache Auflistungsinitialisierer dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c7364-124">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="c7364-125">Der folgende Auflistungsinitialisierer verwendet Objektinitialisierer, um Objekte der `Cat`-Klasse, die in einem vorherigen Beispiel definiert wurden, zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c7364-125">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="c7364-126">Beachten Sie, dass die einzelnen Objektinitialisierer in geschweifte Klammern eingeschlossen und durch Kommas voneinander getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="c7364-126">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="c7364-127">Sie können [NULL](../../../csharp/language-reference/keywords/null.md) als ein Element in einem Auflistungsinitialisierer festlegen, wenn die `Add`-Methode der Auflistung dies zulässt.</span><span class="sxs-lookup"><span data-stu-id="c7364-127">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="c7364-128">Sie können indizierte Elemente angeben, falls die Auflistung  die Indizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7364-128">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a><span data-ttu-id="c7364-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c7364-129">Examples</span></span>

 <span data-ttu-id="c7364-130">Im folgenden Beispiel werden die Konzepte des Objekt- und Auflistungsinitialisierers verbunden.</span><span class="sxs-lookup"><span data-stu-id="c7364-130">The following example combines the concepts of object and collection initializers.</span></span>

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 <span data-ttu-id="c7364-131">Wie im folgenden Beispiel gezeigt wird, ermöglicht ein Objekt, das <xref:System.Collections.IEnumerable> mit einer `Add`-Methode mit mehreren Parametern implementiert, Auflistungsinitialisierer mit mehreren Elementen pro Element in der Liste, die der Signatur der `Add`-Methode entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c7364-131">Shown in the following example, an object which implements <xref:System.Collections.IEnumerable> containing an `Add` method with multiple parameters allows for collection initializers with multiple elements per item in the list corresponding to the signature of the `Add` method.</span></span> 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 <span data-ttu-id="c7364-132">`Add`-Methoden können durch das Schlüsselwort `params` eine variable Anzahl von Argumenten akzeptieren, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c7364-132">`Add` methods can use the `params` keyword to take a variable number of arguments as shown in the following example.</span></span> <span data-ttu-id="c7364-133">Dieses Beispiel zeigt die benutzerdefinierte Implementierung eines Indexers sowie die Initialisierung einer Auflistung mithilfe von Indizes.</span><span class="sxs-lookup"><span data-stu-id="c7364-133">This example demonstrates the custom implementation of an indexer as well to initialize a collection using indexes.</span></span>
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a><span data-ttu-id="c7364-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7364-134">See Also</span></span>  
 [<span data-ttu-id="c7364-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c7364-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c7364-136">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="c7364-136">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="c7364-137">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="c7364-137">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
