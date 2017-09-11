---
title: abstract (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- abstract
- abstract_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a109a8e37f84a2e91229bfce789a69cdc26adba9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-c-reference"></a><span data-ttu-id="2f98b-102">abstract (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2f98b-102">abstract (C# Reference)</span></span>
<span data-ttu-id="2f98b-103">Der `abstract`-Modifizierer gibt an, dass dem modifizierten Objekt eine Implementierung fehlt oder dass diese unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="2f98b-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="2f98b-104">Der abstract-Modifizierer kann für Klassen, Methoden, Eigenschaften, Indexer und Ereignisse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f98b-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="2f98b-105">Verwenden Sie den `abstract`-Modifizierer in einer Klassendeklaration, um anzugeben, dass die Klasse nur die Basisklasse für eine andere Klasse sein soll.</span><span class="sxs-lookup"><span data-stu-id="2f98b-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes.</span></span> <span data-ttu-id="2f98b-106">Als abstrakt markierte Member oder Member in einer abstrakten Klasse müssen von Klassen, die von der abstrakten Klasse abgeleitet wurden, implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2f98b-106">Members marked as abstract, or included in an abstract class, must be implemented by classes that derive from the abstract class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f98b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f98b-107">Example</span></span>  
 <span data-ttu-id="2f98b-108">In diesem Beispiel muss die Klasse `Square` eine Implementierung von `Area` bereitstellen, da sie von `ShapesClass` abgeleitet ist:</span><span class="sxs-lookup"><span data-stu-id="2f98b-108">In this example, the class `Square` must provide an implementation of `Area` because it derives from `ShapesClass`:</span></span>  
  
 <span data-ttu-id="2f98b-109">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f98b-109">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]</span></span>  
  
 <span data-ttu-id="2f98b-110">Abstrakte Klassen weisen die folgenden Funktionen auf:</span><span class="sxs-lookup"><span data-stu-id="2f98b-110">Abstract classes have the following features:</span></span>  
  
-   <span data-ttu-id="2f98b-111">Eine abstrakte Klasse darf nicht instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="2f98b-111">An abstract class cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="2f98b-112">Eine abstrakte Klasse enthält möglicherweise abstrakte Methode und Accessoren.</span><span class="sxs-lookup"><span data-stu-id="2f98b-112">An abstract class may contain abstract methods and accessors.</span></span>  
  
-   <span data-ttu-id="2f98b-113">Eine abstrakte Klasse kann nicht mit dem [sealed](../../../csharp/language-reference/keywords/sealed.md)-Modifizierer geändert werden, da sich die beiden Modifizierer gegenseitig ausschließen.</span><span class="sxs-lookup"><span data-stu-id="2f98b-113">It is not possible to modify an abstract class with the [sealed](../../../csharp/language-reference/keywords/sealed.md) modifier because the two modifers have opposite meanings.</span></span> <span data-ttu-id="2f98b-114">Der `sealed`-Modifizierer verhindert das Vererben einer Klasse, und der `abstract`-Modifizierer erfordert das Vererben einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="2f98b-114">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
-   <span data-ttu-id="2f98b-115">Eine nicht abstrakte Klasse, die von einer abstrakten Klasse abgeleitet wurde, muss Implementierungen aller geerbten abstrakten Methoden und Accessoren enthalten.</span><span class="sxs-lookup"><span data-stu-id="2f98b-115">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="2f98b-116">Verwenden Sie den `abstract`-Modifizierer in einer Methoden- oder Eigenschaftendeklaration, um anzugeben, dass die Methode oder Eigenschaft keine Implementierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="2f98b-116">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="2f98b-117">Abstrakte Methoden weisen die folgenden Funktionen auf:</span><span class="sxs-lookup"><span data-stu-id="2f98b-117">Abstract methods have the following features:</span></span>  
  
-   <span data-ttu-id="2f98b-118">Eine abstrakte Methode ist implizit eine virtuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="2f98b-118">An abstract method is implicitly a virtual method.</span></span>  
  
-   <span data-ttu-id="2f98b-119">Abstrakte Methodendeklarationen sind nur in abstrakten Klassen zulässig.</span><span class="sxs-lookup"><span data-stu-id="2f98b-119">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
-   <span data-ttu-id="2f98b-120">Es gibt keinen Methodenkörper, da eine abstrakte Methodendeklaration keine Implementierungen bietet; die Methodendeklaration enden ganz einfach mit einem Semikolon; auf die Signatur folgen keine geschweiften Klammern ({ }).</span><span class="sxs-lookup"><span data-stu-id="2f98b-120">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="2f98b-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2f98b-121">For example:</span></span>  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="2f98b-122">Die Implementierung wird von der überschreibenden Methode [override](../../../csharp/language-reference/keywords/override.md) zur Verfügung gestellt, die ein Member einer nicht abstrakten Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="2f98b-122">The implementation is provided by an overriding method[override](../../../csharp/language-reference/keywords/override.md), which is a member of a non-abstract class.</span></span>  
  
-   <span data-ttu-id="2f98b-123">Es ist unzulässig, die Modifizierer [static](../../../csharp/language-reference/keywords/static.md) oder [virtual](../../../csharp/language-reference/keywords/virtual.md) in einer abstrakten Methodendeklaration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f98b-123">It is an error to use the [static](../../../csharp/language-reference/keywords/static.md) or [virtual](../../../csharp/language-reference/keywords/virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="2f98b-124">Abstrakte Eigenschaften verhalten sich wie abstrakte Methoden – sie unterscheiden sich lediglich in der Deklarations- und Aufrufsyntax.</span><span class="sxs-lookup"><span data-stu-id="2f98b-124">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="2f98b-125">Es ist ein unzulässig, den `abstract`-Modifizierer für eine statische Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2f98b-125">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="2f98b-126">Eine abstrakte vererbte Eigenschaft kann in einer abgeleiteten Klasse mithilfe der Eigenschaftendeklaration, die den Modifizierer [override](../../../csharp/language-reference/keywords/override.md) verwendet, außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="2f98b-126">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](../../../csharp/language-reference/keywords/override.md) modifier.</span></span>  
  
 <span data-ttu-id="2f98b-127">Weitere Informationen über abstrakte Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="2f98b-127">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="2f98b-128">Eine abstrakte Klasse muss eine Implementierung für alle Schnittstellenmember bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2f98b-128">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="2f98b-129">Eine abstrakte Klasse, die eine Schnittstelle implementiert, ordnet die Schnittstellenmethoden möglicherweise abstrakten Methoden zu.</span><span class="sxs-lookup"><span data-stu-id="2f98b-129">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="2f98b-130">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2f98b-130">For example:</span></span>  
  
 <span data-ttu-id="2f98b-131">[!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f98b-131">[!code-cs[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f98b-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f98b-132">Example</span></span>  
 <span data-ttu-id="2f98b-133">In diesem Beispiel wird die `DerivedClass`-Klasse von der abstrakten Klasse `BaseClass` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2f98b-133">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="2f98b-134">Die abstrakte Klasse enthält eine abstrakte Methode, `AbstractMethod`, und zwei abstrakte Eigenschaften, `X` und `Y`.</span><span class="sxs-lookup"><span data-stu-id="2f98b-134">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
 <span data-ttu-id="2f98b-135">[!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2f98b-135">[!code-cs[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]</span></span>  
  
 <span data-ttu-id="2f98b-136">Wenn Sie beim vorherigen Beispiel versuchen, die abstrakte Klasse mithilfe des folgenden Anweisungsbeispiels zu instanziieren:</span><span class="sxs-lookup"><span data-stu-id="2f98b-136">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 <span data-ttu-id="2f98b-137">erhalten Sie eine Fehlermeldung, dass der Compiler keine Instanz der abstrakten Klasse „BaseClass“ erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="2f98b-137">you will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2f98b-138">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="2f98b-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f98b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f98b-139">See Also</span></span>  
 <span data-ttu-id="2f98b-140">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f98b-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2f98b-141">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f98b-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2f98b-142">[Modifizierer](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="2f98b-142">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="2f98b-143">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="2f98b-143">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 <span data-ttu-id="2f98b-144">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="2f98b-144">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="2f98b-145">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2f98b-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

