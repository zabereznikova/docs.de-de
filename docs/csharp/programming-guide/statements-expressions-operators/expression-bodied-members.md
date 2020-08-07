---
title: Ausdruckskörpermember – C#-Programmierhandbuch
description: Erfahren Sie mehr über Ausdruckskörpermember. Hier finden Sie Codebeispiele, die Ausdruckskörperdefinitionen für Eigenschaften, Konstruktoren, Finalizer und andere Elemente verwenden.
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: e68e96e4aa3ff6a64590459a7197da1833e1a275
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381657"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="c5578-104">Ausdruckskörpermember (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c5578-104">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="c5578-105">Mit Ausdruckstextdefinitionen können Sie die Implementierung eines Members in einer sehr präzisen und lesbaren Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="c5578-105">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="c5578-106">Sie können eine Ausdruckstextdefinition verwenden, wann immer die Logik für einen unterstützten Member, z.B. eine Methode oder Eigenschaft, aus einem einzelnen Ausdruck besteht.</span><span class="sxs-lookup"><span data-stu-id="c5578-106">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="c5578-107">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="c5578-107">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="c5578-108">wobei *expression* ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="c5578-108">where *expression* is a valid expression.</span></span>

<span data-ttu-id="c5578-109">Die Unterstützung für Ausdruckskörperdefinitionen wurde für Methoden und schreibgeschützte Eigenschaften in C# 6 eingeführt und in C# 7.0 erweitert.</span><span class="sxs-lookup"><span data-stu-id="c5578-109">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="c5578-110">Ausdruckstextdefinitionen können mit Typmember verwendet werden, die in der folgenden Tabelle aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="c5578-110">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="c5578-111">Member</span><span class="sxs-lookup"><span data-stu-id="c5578-111">Member</span></span>  |<span data-ttu-id="c5578-112">Unterstützt ab...</span><span class="sxs-lookup"><span data-stu-id="c5578-112">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="c5578-113">Methode</span><span class="sxs-lookup"><span data-stu-id="c5578-113">Method</span></span>](#methods)  |<span data-ttu-id="c5578-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="c5578-114">C# 6</span></span> |
|[<span data-ttu-id="c5578-115">Schreibgeschützte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c5578-115">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="c5578-116">C# 6</span><span class="sxs-lookup"><span data-stu-id="c5578-116">C# 6</span></span>  |
|[<span data-ttu-id="c5578-117">Property</span><span class="sxs-lookup"><span data-stu-id="c5578-117">Property</span></span>](#properties)  |<span data-ttu-id="c5578-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="c5578-118">C# 7.0</span></span> |
|[<span data-ttu-id="c5578-119">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="c5578-119">Constructor</span></span>](#constructors)   |<span data-ttu-id="c5578-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="c5578-120">C# 7.0</span></span> |
|[<span data-ttu-id="c5578-121">Finalizer</span><span class="sxs-lookup"><span data-stu-id="c5578-121">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="c5578-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="c5578-122">C# 7.0</span></span> |
|[<span data-ttu-id="c5578-123">Indexer</span><span class="sxs-lookup"><span data-stu-id="c5578-123">Indexer</span></span>](#indexers)       |<span data-ttu-id="c5578-124">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="c5578-124">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="c5578-125">Methoden</span><span class="sxs-lookup"><span data-stu-id="c5578-125">Methods</span></span>

<span data-ttu-id="c5578-126">Eine Ausdruckskörpermethode besteht aus einem einzelnen Ausdruck, der einen Wert zurückgibt, dessen Typ mit dem Rückgabetyp der Methode übereinstimmt bzw. für Methoden, die `void` zurückgeben, das einige Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="c5578-126">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="c5578-127">Beispielsweise enthalten Typen, die die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen normalerweise einen einzelnen Ausdruck, der die Zeichenfolgendarstellung des aktuellen Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c5578-127">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="c5578-128">Das folgende Beispiel definiert eine `Person`-Klasse, die die <xref:System.Object.ToString%2A>-Methode mit einer Ausdruckstextmethode außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="c5578-128">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="c5578-129">Es wird auch eine `DisplayName`-Methode definiert, die einen Namen für die Konsole anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c5578-129">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="c5578-130">Beachten Sie, dass das Schlüsselwort `return` nicht in der Ausdruckstextmethode `ToString` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5578-130">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="c5578-131">Weitere Informationen finden Sie unter [Methoden (C#-Programmierhandbuch)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="c5578-131">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="c5578-132">Schreibgeschützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c5578-132">Read-only properties</span></span>

<span data-ttu-id="c5578-133">Ab C# 6 können Sie Ausdruckskörperdefinitionen zum Implementieren von schreibgeschützten Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5578-133">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="c5578-134">Verwenden Sie hierzu die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="c5578-134">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="c5578-135">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren schreibgeschützte Eigenschaft `Name` als Ausdruckskörperdefinition implementiert wird, die den Wert des privaten `locationName`-Felds zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="c5578-135">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="c5578-136">Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="c5578-136">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="c5578-137">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c5578-137">Properties</span></span>

<span data-ttu-id="c5578-138">Ab C# 7.0 können Sie Ausdruckskörperdefinitionen zum Implementieren von `get`-Eigenschaften und `set`-Accessoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5578-138">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="c5578-139">Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c5578-139">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="c5578-140">Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="c5578-140">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="c5578-141">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="c5578-141">Constructors</span></span>

<span data-ttu-id="c5578-142">Eine Ausdruckstextdefinition für einen Konstruktor enthält in der Regel einen einzelnen Zuweisungsausdruck oder einen Methodenaufruf, der die Argumente des Konstruktors behandelt oder den Instanzzustand initialisiert.</span><span class="sxs-lookup"><span data-stu-id="c5578-142">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="c5578-143">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="c5578-143">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="c5578-144">Die Ausdruckstextdefinition weist das Argument für die Eigenschaft `Name` zu.</span><span class="sxs-lookup"><span data-stu-id="c5578-144">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="c5578-145">Weitere Informationen finden Sie unter [Konstruktoren (C#-Programmierhandbuch)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="c5578-145">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="c5578-146">Finalizer</span><span class="sxs-lookup"><span data-stu-id="c5578-146">Finalizers</span></span>

<span data-ttu-id="c5578-147">Eine Ausdruckstextdefinition für einen Finalizer enthält normalerweise Bereinigungsanweisungen, z.B. Anweisungen, die nicht verwaltete Ressourcen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c5578-147">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="c5578-148">Im folgenden Beispiel wird ein Finalizer definiert, der eine Ausdruckstextdefinition verwendet, um anzugeben, dass der Finalizer aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c5578-148">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="c5578-149">Weitere Informationen finden Sie unter [Finalizer (C#-Programmierhandbuch)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="c5578-149">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="c5578-150">Indexer</span><span class="sxs-lookup"><span data-stu-id="c5578-150">Indexers</span></span>

<span data-ttu-id="c5578-151">Genauso wie Eigenschaften bestehen die `get`- und `set`-Accessoren des Indexers aus Ausdruckstextdefinitionen, wenn der `get`-Accessor aus einem einzelnen Ausdruck besteht, der einen Wert zurückgibt, oder der `set`-Accessor führt eine einfache Zuweisung aus.</span><span class="sxs-lookup"><span data-stu-id="c5578-151">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="c5578-152">Im folgenden Beispiel wird eine Klasse namens `Sports` definiert, die ein internes <xref:System.String>-Array enthält, das aus den Namen von verschiedenen Sportarten besteht.</span><span class="sxs-lookup"><span data-stu-id="c5578-152">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="c5578-153">Die `get`- und `set`-Accessoren des Indexers werden als Ausdruckstextdefinitionen implementiert.</span><span class="sxs-lookup"><span data-stu-id="c5578-153">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="c5578-154">Weitere Informationen finden Sie unter [Indexer (C#-Programmierhandbuch)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c5578-154">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
