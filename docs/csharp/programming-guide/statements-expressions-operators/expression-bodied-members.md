---
title: "Ausdruckskörpermember (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ead1e474fe87bd9fbd0f972bc0f2fc4fefc12ecf
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2017
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="b3ddb-102">Ausdruckskörpermember (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b3ddb-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="b3ddb-103">Mit Ausdruckstextdefinitionen können Sie die Implementierung eines Members in einer sehr präzisen und lesbaren Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="b3ddb-104">Sie können eine Ausdruckstextdefinition verwenden, wann immer die Logik für einen unterstützten Member, z.B. eine Methode oder Eigenschaft, aus einem einzelnen Ausdruck besteht.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="b3ddb-105">Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:</span><span class="sxs-lookup"><span data-stu-id="b3ddb-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="b3ddb-106">wobei *expression* ein gültiger Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="b3ddb-107">Die Unterstützung für Ausdruckstextdefinitionen wurde für Methoden und Get-Eigenschaftenzugriffsmethoden in C# 6 eingeführt und in C# 7 erweitert.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.</span></span> <span data-ttu-id="b3ddb-108">Ausdruckstextdefinitionen können mit Typmember verwendet werden, die in der folgenden Tabelle aufgeführt sind:</span><span class="sxs-lookup"><span data-stu-id="b3ddb-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="b3ddb-109">Member</span><span class="sxs-lookup"><span data-stu-id="b3ddb-109">Member</span></span>  |<span data-ttu-id="b3ddb-110">Unterstützt ab...</span><span class="sxs-lookup"><span data-stu-id="b3ddb-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="b3ddb-111">Methode</span><span class="sxs-lookup"><span data-stu-id="b3ddb-111">Method</span></span>](#methods)  |<span data-ttu-id="b3ddb-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="b3ddb-112">C# 6</span></span> |
|[<span data-ttu-id="b3ddb-113">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="b3ddb-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="b3ddb-114">C# 7</span><span class="sxs-lookup"><span data-stu-id="b3ddb-114">C# 7</span></span> |
|[<span data-ttu-id="b3ddb-115">Finalizer</span><span class="sxs-lookup"><span data-stu-id="b3ddb-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="b3ddb-116">C# 7</span><span class="sxs-lookup"><span data-stu-id="b3ddb-116">C# 7</span></span> |
|[<span data-ttu-id="b3ddb-117">Get-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b3ddb-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="b3ddb-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="b3ddb-118">C# 6</span></span> |
|[<span data-ttu-id="b3ddb-119">Set-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b3ddb-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="b3ddb-120">C# 7</span><span class="sxs-lookup"><span data-stu-id="b3ddb-120">C# 7</span></span> |
|[<span data-ttu-id="b3ddb-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="b3ddb-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="b3ddb-122">C# 7</span><span class="sxs-lookup"><span data-stu-id="b3ddb-122">C# 7</span></span> |

## <a name="methods"></a><span data-ttu-id="b3ddb-123">Methoden</span><span class="sxs-lookup"><span data-stu-id="b3ddb-123">Methods</span></span>

<span data-ttu-id="b3ddb-124">Eine Ausdruckskörpermethode besteht aus einem einzelnen Ausdruck, der einen Wert zurückgibt, dessen Typ mit dem Rückgabetyp der Methode übereinstimmt bzw. für Methoden, die `void` zurückgeben, das einige Vorgänge ausführt.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="b3ddb-125">Beispielsweise enthalten Typen, die die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen normalerweise einen einzelnen Ausdruck, der die Zeichenfolgendarstellung des aktuellen Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="b3ddb-126">Das folgende Beispiel definiert eine `Person`-Klasse, die die <xref:System.Object.ToString%2A>-Methode mit einer Ausdruckstextmethode außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="b3ddb-127">Es wird auch eine `Show`-Methode definiert, die einen Namen für die Konsole anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-127">It also defines a `Show` method that displays a name to the console.</span></span> <span data-ttu-id="b3ddb-128">Beachten Sie, dass das Schlüsselwort `return` nicht in der Ausdruckstextmethode `ToString` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="b3ddb-129">Weitere Informationen finden Sie unter [Methoden (C#-Programmierhandbuch)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="b3ddb-130">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="b3ddb-130">Constructors</span></span>

<span data-ttu-id="b3ddb-131">Eine Ausdruckstextdefinition für einen Konstruktor enthält in der Regel einen einzelnen Zuweisungsausdruck oder einen Methodenaufruf, der die Argumente des Konstruktors behandelt oder den Instanzzustand initialisiert.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-131">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="b3ddb-132">Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-132">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="b3ddb-133">Die Ausdruckstextdefinition weist das Argument für die Eigenschaft `Name` zu.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-133">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="b3ddb-134">Weitere Informationen finden Sie unter [Konstruktoren (C#-Programmierhandbuch)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-134">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="b3ddb-135">Finalizer</span><span class="sxs-lookup"><span data-stu-id="b3ddb-135">Finalizers</span></span>

<span data-ttu-id="b3ddb-136">Eine Ausdruckstextdefinition für einen Finalizer enthält normalerweise Bereinigungsanweisungen, z.B. Anweisungen, die nicht verwaltete Ressourcen veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-136">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="b3ddb-137">Im folgenden Beispiel wird ein Finalizer definiert, der eine Ausdruckstextdefinition verwendet, um anzugeben, dass der Finalizer aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-137">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="b3ddb-138">Weitere Informationen finden Sie unter [Finalizer (C#-Programmierhandbuch)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-138">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="b3ddb-139">Anweisungen der Get-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b3ddb-139">Property get statements</span></span>

<span data-ttu-id="b3ddb-140">Wenn Sie selbst einen Accessor der Get-Methode der Eigenschaft implementieren möchten, können Sie eine Ausdruckstextdefinition für Eigenschaftswerte verwenden, die den Eigenschaftswert einfach zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-140">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="b3ddb-141">Beachten sie, dass die Anweisung `return` nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-141">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="b3ddb-142">Im folgenden Beispiel wird eine `Location.Name`-Anweisung definiert, deren Accessor der Get-Methode der Eigenschaft den Wert des privaten `locationName`-Felds zurückgibt, das hinter der Eigenschaft liegt.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-142">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="b3ddb-143">Schreibgeschützte Eigenschaften, die eine Ausdruckstextdefinition verwenden, können ohne explizite `set`-Anweisung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-143">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="b3ddb-144">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="b3ddb-144">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="b3ddb-145">Das folgende Beispiel definiert eine `Location`-Klasse, deren schreibgeschützte Eigenschaft `Name` als Ausdruckstextdefinition implementiert wird, die den Wert des privaten `locationName`-Felds zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-145">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="b3ddb-146">Weitere Informationen finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-146">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="b3ddb-147">Anweisungen der Set-Methode der Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b3ddb-147">Property set statements</span></span>

<span data-ttu-id="b3ddb-148">Wenn Sie selbst einen Accessor der Set-Methode der Eigenschaft implementieren möchten, können Sie eine Ausdruckstextdefinition für einen Ausdruck mit nur einer Zeile verwenden, der dem Feld einen Wert zuweist, das hinter der Eigenschaft steht.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-148">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="b3ddb-149">Im folgenden Beispiel wird eine `Location.Name`-Eigenschaft definiert, deren Set-Methode der Eigenschaft das Eingabeargument dem privaten `locationName`-Feld zuweist, das hinter der Eigenschaft steht.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-149">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="b3ddb-150">Weitere Informationen finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-150">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="b3ddb-151">Indexer</span><span class="sxs-lookup"><span data-stu-id="b3ddb-151">Indexers</span></span>

<span data-ttu-id="b3ddb-152">Genauso wie Eigenschaften bestehen die Accessoren der Get- und Set-Methode des Indexers aus Ausdruckstextdefinitionen, wenn der Get-Accessor aus einer einzelnen Anweisung besteht, die einen Wert zurückgibt, oder der Set-Accessor führt eine einfache Zuweisung aus.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-152">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="b3ddb-153">Im folgenden Beispiel wird eine Klasse namens `Sports` definiert, die ein internes <xref:System.String>-Array enthält, das aus den Namen von verschiedenen Sportarten besteht.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-153">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="b3ddb-154">Die Get- und Set-Accessoren des Indexers werden als Ausdruckstextdefinitionen implementiert.</span><span class="sxs-lookup"><span data-stu-id="b3ddb-154">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

<span data-ttu-id="b3ddb-155">Weitere Informationen finden Sie unter [Indexer (C#-Programmierhandbuch)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b3ddb-155">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>

