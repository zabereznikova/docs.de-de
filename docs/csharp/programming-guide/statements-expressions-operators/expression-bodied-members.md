---
title: Ausdruckskörpermember – C#-Programmierhandbuch
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711986"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="b2d5b-102">Ausdruckskörpermember (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b2d5b-102">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="b2d5b-103">Mit Ausdruckstextdefinitionen können Sie die Implementierung eines Members in einer sehr präzisen und lesbaren Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="b2d5b-104">Sie können eine Ausdruckstextdefinition verwenden, wann immer die Logik für einen unterstützten Member, z.B. eine Methode oder Eigenschaft, aus einem einzelnen Ausdruck besteht.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="b2d5b-105">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="b2d5b-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="b2d5b-106">wobei *expression* ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-106">where *expression* is a valid expression.</span></span>

<span data-ttu-id="b2d5b-107">Die Unterstützung für Ausdruckskörperdefinitionen wurde für Methoden und schreibgeschützte Eigenschaften in C# 6 eingeführt und in C# 7.0 erweitert.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-107">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="b2d5b-108">Ausdruckstextdefinitionen können mit Typmember verwendet werden, die in der folgenden Tabelle aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="b2d5b-108">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="b2d5b-109">Member</span><span class="sxs-lookup"><span data-stu-id="b2d5b-109">Member</span></span>  |<span data-ttu-id="b2d5b-110">Unterstützt ab...</span><span class="sxs-lookup"><span data-stu-id="b2d5b-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="b2d5b-111">Methode</span><span class="sxs-lookup"><span data-stu-id="b2d5b-111">Method</span></span>](#methods)  |<span data-ttu-id="b2d5b-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="b2d5b-112">C# 6</span></span> |
|[<span data-ttu-id="b2d5b-113">Schreibgeschützte Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b2d5b-113">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="b2d5b-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="b2d5b-114">C# 6</span></span>  |
|[<span data-ttu-id="b2d5b-115">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b2d5b-115">Property</span></span>](#properties)  |<span data-ttu-id="b2d5b-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b2d5b-116">C# 7.0</span></span> |
|[<span data-ttu-id="b2d5b-117">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="b2d5b-117">Constructor</span></span>](#constructors)   |<span data-ttu-id="b2d5b-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b2d5b-118">C# 7.0</span></span> |
|[<span data-ttu-id="b2d5b-119">Finalizer</span><span class="sxs-lookup"><span data-stu-id="b2d5b-119">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="b2d5b-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b2d5b-120">C# 7.0</span></span> |
|[<span data-ttu-id="b2d5b-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="b2d5b-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="b2d5b-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="b2d5b-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="b2d5b-123">Methoden</span><span class="sxs-lookup"><span data-stu-id="b2d5b-123">Methods</span></span>

<span data-ttu-id="b2d5b-124">Eine Ausdruckskörpermethode besteht aus einem einzelnen Ausdruck, der einen Wert zurückgibt, dessen Typ mit dem Rückgabetyp der Methode übereinstimmt bzw. für Methoden, die `void` zurückgeben, das einige Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="b2d5b-125">Beispielsweise enthalten Typen, die die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen normalerweise einen einzelnen Ausdruck, der die Zeichenfolgendarstellung des aktuellen Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="b2d5b-126">Das folgende Beispiel definiert eine `Person`-Klasse, die die <xref:System.Object.ToString%2A>-Methode mit einer Ausdruckstextmethode außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="b2d5b-127">Es wird auch eine `DisplayName`-Methode definiert, die einen Namen für die Konsole anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="b2d5b-128">Beachten Sie, dass das Schlüsselwort `return` nicht in der Ausdruckstextmethode `ToString` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="b2d5b-129">Weitere Informationen finden Sie unter [Methoden (C#-Programmierhandbuch)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="b2d5b-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="b2d5b-130">Schreibgeschützte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b2d5b-130">Read-only properties</span></span>

<span data-ttu-id="b2d5b-131">Ab C# 6 können Sie Ausdruckskörperdefinitionen zum Implementieren von schreibgeschützten Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-131">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="b2d5b-132">Verwenden Sie hierzu die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="b2d5b-132">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="b2d5b-133">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren schreibgeschützte Eigenschaft `Name` als Ausdruckskörperdefinition implementiert wird, die den Wert des privaten `locationName`-Felds zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="b2d5b-133">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="b2d5b-134">Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="b2d5b-134">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="b2d5b-135">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b2d5b-135">Properties</span></span>

<span data-ttu-id="b2d5b-136">Ab C# 7.0 können Sie Ausdruckskörperdefinitionen zum Implementieren von `get`-Eigenschaften und `set`-Accessoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-136">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="b2d5b-137">Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b2d5b-137">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="b2d5b-138">Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="b2d5b-138">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="b2d5b-139">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="b2d5b-139">Constructors</span></span>

<span data-ttu-id="b2d5b-140">Eine Ausdruckstextdefinition für einen Konstruktor enthält in der Regel einen einzelnen Zuweisungsausdruck oder einen Methodenaufruf, der die Argumente des Konstruktors behandelt oder den Instanzzustand initialisiert.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-140">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="b2d5b-141">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-141">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="b2d5b-142">Die Ausdruckstextdefinition weist das Argument für die Eigenschaft `Name` zu.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-142">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="b2d5b-143">Weitere Informationen finden Sie unter [Konstruktoren (C#-Programmierhandbuch)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b2d5b-143">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="b2d5b-144">Finalizer</span><span class="sxs-lookup"><span data-stu-id="b2d5b-144">Finalizers</span></span>

<span data-ttu-id="b2d5b-145">Eine Ausdruckstextdefinition für einen Finalizer enthält normalerweise Bereinigungsanweisungen, z.B. Anweisungen, die nicht verwaltete Ressourcen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-145">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="b2d5b-146">Im folgenden Beispiel wird ein Finalizer definiert, der eine Ausdruckstextdefinition verwendet, um anzugeben, dass der Finalizer aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-146">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="b2d5b-147">Weitere Informationen finden Sie unter [Finalizer (C#-Programmierhandbuch)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="b2d5b-147">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="b2d5b-148">Indexer</span><span class="sxs-lookup"><span data-stu-id="b2d5b-148">Indexers</span></span>

<span data-ttu-id="b2d5b-149">Genauso wie Eigenschaften bestehen die `get`- und `set`-Accessoren des Indexers aus Ausdruckstextdefinitionen, wenn der `get`-Accessor aus einem einzelnen Ausdruck besteht, der einen Wert zurückgibt, oder der `set`-Accessor führt eine einfache Zuweisung aus.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-149">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="b2d5b-150">Im folgenden Beispiel wird eine Klasse namens `Sports` definiert, die ein internes <xref:System.String>-Array enthält, das aus den Namen von verschiedenen Sportarten besteht.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-150">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="b2d5b-151">Die `get`- und `set`-Accessoren des Indexers werden als Ausdruckstextdefinitionen implementiert.</span><span class="sxs-lookup"><span data-stu-id="b2d5b-151">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="b2d5b-152">Weitere Informationen finden Sie unter [Indexer (C#-Programmierhandbuch)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2d5b-152">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
