---
title: "Ausdruckskörpermember (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d12f9f3af9a57e142311f6d1676b5f97e8b60d19
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="ff90d-102">Ausdruckskörpermember (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ff90d-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="ff90d-103">Mit Ausdruckstextdefinitionen können Sie die Implementierung eines Members in einer sehr präzisen und lesbaren Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="ff90d-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="ff90d-104">Sie können eine Ausdruckstextdefinition verwenden, wann immer die Logik für einen unterstützten Member, z.B. eine Methode oder Eigenschaft, aus einem einzelnen Ausdruck besteht.</span><span class="sxs-lookup"><span data-stu-id="ff90d-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="ff90d-105">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="ff90d-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="ff90d-106">wobei *expression* ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="ff90d-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="ff90d-107">Die Unterstützung für Ausdruckstextdefinitionen wurde für Methoden und Get-Eigenschaftenzugriffsmethoden in C# 6 eingeführt und in C# 7 erweitert.</span><span class="sxs-lookup"><span data-stu-id="ff90d-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.</span></span> <span data-ttu-id="ff90d-108">Ausdruckstextdefinitionen können mit Typmember verwendet werden, die in der folgenden Tabelle aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="ff90d-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="ff90d-109">Member</span><span class="sxs-lookup"><span data-stu-id="ff90d-109">Member</span></span>  |<span data-ttu-id="ff90d-110">Unterstützt ab...</span><span class="sxs-lookup"><span data-stu-id="ff90d-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="ff90d-111">Methode</span><span class="sxs-lookup"><span data-stu-id="ff90d-111">Method</span></span>](#methods)  |<span data-ttu-id="ff90d-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="ff90d-112">C# 6</span></span> |
|[<span data-ttu-id="ff90d-113">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="ff90d-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="ff90d-114">C# 7</span><span class="sxs-lookup"><span data-stu-id="ff90d-114">C# 7</span></span> |
|[<span data-ttu-id="ff90d-115">Finalizer</span><span class="sxs-lookup"><span data-stu-id="ff90d-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="ff90d-116">C# 7</span><span class="sxs-lookup"><span data-stu-id="ff90d-116">C# 7</span></span> |
|[<span data-ttu-id="ff90d-117">Get-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ff90d-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="ff90d-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="ff90d-118">C# 6</span></span> |
|[<span data-ttu-id="ff90d-119">Set-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ff90d-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="ff90d-120">C# 7</span><span class="sxs-lookup"><span data-stu-id="ff90d-120">C# 7</span></span> |
|[<span data-ttu-id="ff90d-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="ff90d-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="ff90d-122">C# 7</span><span class="sxs-lookup"><span data-stu-id="ff90d-122">C# 7</span></span> |

## <a name="methods"></a><span data-ttu-id="ff90d-123">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff90d-123">Methods</span></span>

<span data-ttu-id="ff90d-124">Eine Ausdruckskörpermethode besteht aus einem einzelnen Ausdruck, der einen Wert zurückgibt, dessen Typ mit dem Rückgabetyp der Methode übereinstimmt bzw. für Methoden, die `void` zurückgeben, das einige Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="ff90d-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="ff90d-125">Beispielsweise enthalten Typen, die die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen normalerweise einen einzelnen Ausdruck, der die Zeichenfolgendarstellung des aktuellen Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ff90d-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="ff90d-126">Das folgende Beispiel definiert eine `Person`-Klasse, die die <xref:System.Object.ToString%2A>-Methode mit einer Ausdruckstextmethode außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="ff90d-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="ff90d-127">Es wird auch eine `Show`-Methode definiert, die einen Namen für die Konsole anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff90d-127">It also defines a `Show` method that displays a name to the console.</span></span> <span data-ttu-id="ff90d-128">Beachten Sie, dass das Schlüsselwort `return` nicht in der Ausdruckstextmethode `ToString` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff90d-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

<span data-ttu-id="ff90d-129">[!code-cs[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-129">[!code-cs[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]</span></span>  

<span data-ttu-id="ff90d-130">Weitere Informationen finden Sie unter [Methoden (C#-Programmierhandbuch)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="ff90d-130">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="ff90d-131">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="ff90d-131">Constructors</span></span>

<span data-ttu-id="ff90d-132">Eine Ausdruckstextdefinition für einen Konstruktor enthält in der Regel einen einzelnen Zuweisungsausdruck oder einen Methodenaufruf, der die Argumente des Konstruktors behandelt oder den Instanzzustand initialisiert.</span><span class="sxs-lookup"><span data-stu-id="ff90d-132">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="ff90d-133">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="ff90d-133">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="ff90d-134">Die Ausdruckstextdefinition weist das Argument für die Eigenschaft `Name` zu.</span><span class="sxs-lookup"><span data-stu-id="ff90d-134">The expression body definition assigns the argument to the `Name` property.</span></span>

<span data-ttu-id="ff90d-135">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-135">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

<span data-ttu-id="ff90d-136">Weitere Informationen finden Sie unter [Konstruktoren (C#-Programmierhandbuch)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="ff90d-136">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="ff90d-137">Finalizer</span><span class="sxs-lookup"><span data-stu-id="ff90d-137">Finalizers</span></span>

<span data-ttu-id="ff90d-138">Eine Ausdruckstextdefinition für einen Finalizer enthält normalerweise Bereinigungsanweisungen, z.B. Anweisungen, die nicht verwaltete Ressourcen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="ff90d-138">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="ff90d-139">Im folgenden Beispiel wird ein Finalizer definiert, der eine Ausdruckstextdefinition verwendet, um anzugeben, dass der Finalizer aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff90d-139">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

<span data-ttu-id="ff90d-140">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-140">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span></span>  

<span data-ttu-id="ff90d-141">Weitere Informationen finden Sie unter [Finalizer (C#-Programmierhandbuch)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="ff90d-141">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="ff90d-142">Anweisungen der Get-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ff90d-142">Property get statements</span></span>

<span data-ttu-id="ff90d-143">Wenn Sie selbst einen Accessor der Get-Methode der Eigenschaft implementieren möchten, können Sie eine Ausdruckstextdefinition für Eigenschaftswerte verwenden, die den Eigenschaftswert einfach zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ff90d-143">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="ff90d-144">Beachten sie, dass die Anweisung `return` nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff90d-144">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="ff90d-145">Im folgenden Beispiel wird eine `Location.Name`-Anweisung definiert, deren Accessor der Get-Methode der Eigenschaft den Wert des privaten `locationName`-Felds zurückgibt, das hinter der Eigenschaft liegt.</span><span class="sxs-lookup"><span data-stu-id="ff90d-145">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

<span data-ttu-id="ff90d-146">[!code-cs[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-146">[!code-cs[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

<span data-ttu-id="ff90d-147">Schreibgeschützte Eigenschaften, die eine Ausdruckstextdefinition verwenden, können ohne explizite `set`-Anweisung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff90d-147">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="ff90d-148">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="ff90d-148">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="ff90d-149">Das folgende Beispiel definiert eine `Location`-Klasse, deren schreibgeschützte Eigenschaft `Name` als Ausdruckstextdefinition implementiert wird, die den Wert des privaten `locationName`-Felds zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ff90d-149">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

<span data-ttu-id="ff90d-150">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-150">[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]</span></span>  

<span data-ttu-id="ff90d-151">Weitere Informationen finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="ff90d-151">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="ff90d-152">Anweisungen der Set-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ff90d-152">Property set statements</span></span>

<span data-ttu-id="ff90d-153">Wenn Sie selbst einen Accessor der Set-Methode der Eigenschaft implementieren möchten, können Sie eine Ausdruckstextdefinition für einen Ausdruck mit nur einer Zeile verwenden, der dem Feld einen Wert zuweist, das hinter der Eigenschaft steht.</span><span class="sxs-lookup"><span data-stu-id="ff90d-153">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="ff90d-154">Im folgenden Beispiel wird eine `Location.Name`-Eigenschaft definiert, deren Set-Methode der Eigenschaft das Eingabeargument dem privaten `locationName`-Feld zuweist, das hinter der Eigenschaft steht.</span><span class="sxs-lookup"><span data-stu-id="ff90d-154">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

<span data-ttu-id="ff90d-155">[!code-cs[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-155">[!code-cs[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]</span></span>  

<span data-ttu-id="ff90d-156">Weitere Informationen finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="ff90d-156">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="ff90d-157">Indexer</span><span class="sxs-lookup"><span data-stu-id="ff90d-157">Indexers</span></span>

<span data-ttu-id="ff90d-158">Genauso wie Eigenschaften bestehen die Accessoren der Get- und Set-Methode des Indexers aus Ausdruckstextdefinitionen, wenn der Get-Accessor aus einer einzelnen Anweisung besteht, die einen Wert zurückgibt, oder der Set-Accessor führt eine einfache Zuweisung aus.</span><span class="sxs-lookup"><span data-stu-id="ff90d-158">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="ff90d-159">Im folgenden Beispiel wird eine Klasse namens `Sports` definiert, die ein internes <xref:System.String>-Array enthält, das aus den Namen von verschiedenen Sportarten besteht.</span><span class="sxs-lookup"><span data-stu-id="ff90d-159">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="ff90d-160">Die Get- und Set-Accessoren des Indexers werden als Ausdruckstextdefinitionen implementiert.</span><span class="sxs-lookup"><span data-stu-id="ff90d-160">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

<span data-ttu-id="ff90d-161">[!code-cs[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ff90d-161">[!code-cs[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]</span></span> 

<span data-ttu-id="ff90d-162">Weitere Informationen finden Sie unter [Indexer (C#-Programmierhandbuch)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff90d-162">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>


