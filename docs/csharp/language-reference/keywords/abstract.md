---
description: abstract – C#-Referenz
title: abstract – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 095c4dea838aff4f14833d78fb10a2f831cf5173
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89127203"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="f40dd-103">abstract (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f40dd-103">abstract (C# Reference)</span></span>
<span data-ttu-id="f40dd-104">Der `abstract`-Modifizierer gibt an, dass dem modifizierten Objekt eine Implementierung fehlt oder dass diese unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="f40dd-104">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="f40dd-105">Der abstract-Modifizierer kann für Klassen, Methoden, Eigenschaften, Indexer und Ereignisse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f40dd-105">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="f40dd-106">Verwenden Sie den `abstract`-Modifizierer in einer Klassendeklaration, um anzugeben, dass die Klasse nur die Basisklasse für andere Klassen sein und nicht selbst instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f40dd-106">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes, not instantiated on its own.</span></span> <span data-ttu-id="f40dd-107">Als abstrakt markierte Member müssen von Klassen, die von nicht abstrakten Klassen abgeleitet wurden, implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f40dd-107">Members marked as abstract must be implemented by non-abstract classes that derive from the abstract class.</span></span>
  
## <a name="example"></a><span data-ttu-id="f40dd-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f40dd-108">Example</span></span>  
 <span data-ttu-id="f40dd-109">In diesem Beispiel muss die Klasse `Square` eine Implementierung von `GetArea` bereitstellen, da sie von `Shape` abgeleitet ist:</span><span class="sxs-lookup"><span data-stu-id="f40dd-109">In this example, the class `Square` must provide an implementation of `GetArea` because it derives from `Shape`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="f40dd-110">Abstrakte Klassen weisen die folgenden Funktionen auf:</span><span class="sxs-lookup"><span data-stu-id="f40dd-110">Abstract classes have the following features:</span></span>  
  
- <span data-ttu-id="f40dd-111">Eine abstrakte Klasse darf nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="f40dd-111">An abstract class cannot be instantiated.</span></span>  
  
- <span data-ttu-id="f40dd-112">Eine abstrakte Klasse enthält möglicherweise abstrakte Methode und Accessoren.</span><span class="sxs-lookup"><span data-stu-id="f40dd-112">An abstract class may contain abstract methods and accessors.</span></span>  
  
- <span data-ttu-id="f40dd-113">Eine abstrakte Klasse kann nicht mit dem [sealed](./sealed.md)-Modifizierer geändert werden, da sich die beiden Modifizierer gegenseitig ausschließen.</span><span class="sxs-lookup"><span data-stu-id="f40dd-113">It is not possible to modify an abstract class with the [sealed](./sealed.md) modifier because the two modifiers have opposite meanings.</span></span> <span data-ttu-id="f40dd-114">Der `sealed`-Modifizierer verhindert das Vererben einer Klasse, und der `abstract`-Modifizierer erfordert das Vererben einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="f40dd-114">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
- <span data-ttu-id="f40dd-115">Eine nicht abstrakte Klasse, die von einer abstrakten Klasse abgeleitet wurde, muss Implementierungen aller geerbten abstrakten Methoden und Accessoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="f40dd-115">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="f40dd-116">Verwenden Sie den `abstract`-Modifizierer in einer Methoden- oder Eigenschaftendeklaration, um anzugeben, dass die Methode oder Eigenschaft keine Implementierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="f40dd-116">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="f40dd-117">Abstrakte Methoden weisen die folgenden Funktionen auf:</span><span class="sxs-lookup"><span data-stu-id="f40dd-117">Abstract methods have the following features:</span></span>  
  
- <span data-ttu-id="f40dd-118">Eine abstrakte Methode ist implizit eine virtuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="f40dd-118">An abstract method is implicitly a virtual method.</span></span>  
  
- <span data-ttu-id="f40dd-119">Abstrakte Methodendeklarationen sind nur in abstrakten Klassen zulässig.</span><span class="sxs-lookup"><span data-stu-id="f40dd-119">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
- <span data-ttu-id="f40dd-120">Es gibt keinen Methodenkörper, da eine abstrakte Methodendeklaration keine Implementierungen bietet; die Methodendeklaration enden ganz einfach mit einem Semikolon; auf die Signatur folgen keine geschweiften Klammern ({ }).</span><span class="sxs-lookup"><span data-stu-id="f40dd-120">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="f40dd-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f40dd-121">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="f40dd-122">Die Implementierung wird von der Methode [override](./override.md) zur Verfügung gestellt, die ein Member einer nicht abstrakten Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="f40dd-122">The implementation is provided by a method [override](./override.md), which is a member of a non-abstract class.</span></span>  
  
- <span data-ttu-id="f40dd-123">Es ist unzulässig, die Modifizierer [static](./static.md) oder [virtual](./virtual.md) in einer abstrakten Methodendeklaration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f40dd-123">It is an error to use the [static](./static.md) or [virtual](./virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="f40dd-124">Abstrakte Eigenschaften verhalten sich wie abstrakte Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.</span><span class="sxs-lookup"><span data-stu-id="f40dd-124">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
- <span data-ttu-id="f40dd-125">Es ist ein unzulässig, den `abstract`-Modifizierer für eine statische Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f40dd-125">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
- <span data-ttu-id="f40dd-126">Eine abstrakte vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer [override](./override.md) verwendet, außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f40dd-126">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](./override.md) modifier.</span></span>  
  
 <span data-ttu-id="f40dd-127">Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="f40dd-127">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="f40dd-128">Eine abstrakte Klasse muss eine Implementierung für alle Schnittstellenmember bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f40dd-128">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="f40dd-129">Eine abstrakte Klasse, die eine Schnittstelle implementiert, ordnet die Schnittstellenmethoden möglicherweise abstrakten Methoden zu.</span><span class="sxs-lookup"><span data-stu-id="f40dd-129">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="f40dd-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f40dd-130">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="f40dd-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f40dd-131">Example</span></span>  
 <span data-ttu-id="f40dd-132">In diesem Beispiel wird die `DerivedClass`-Klasse von der abstrakten Klasse `BaseClass` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f40dd-132">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="f40dd-133">Die abstrakte Klasse enthält eine abstrakte Methode, `AbstractMethod`, und zwei abstrakte Eigenschaften, `X` und `Y`.</span><span class="sxs-lookup"><span data-stu-id="f40dd-133">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="f40dd-134">Wenn Sie beim vorherigen Beispiel versuchen, die abstrakte Klasse mithilfe des folgenden Anweisungsbeispiels zu instanziieren:</span><span class="sxs-lookup"><span data-stu-id="f40dd-134">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="f40dd-135">Sie erhalten eine Fehlermeldung, dass der Compiler keine Instanz der abstrakten Klasse „BaseClass“ erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f40dd-135">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f40dd-136">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f40dd-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f40dd-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f40dd-137">See also</span></span>

- [<span data-ttu-id="f40dd-138">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f40dd-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f40dd-139">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f40dd-139">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f40dd-140">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="f40dd-140">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f40dd-141">virtual</span><span class="sxs-lookup"><span data-stu-id="f40dd-141">virtual</span></span>](./virtual.md)
- [<span data-ttu-id="f40dd-142">override</span><span class="sxs-lookup"><span data-stu-id="f40dd-142">override</span></span>](./override.md)
- [<span data-ttu-id="f40dd-143">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f40dd-143">C# Keywords</span></span>](./index.md)
