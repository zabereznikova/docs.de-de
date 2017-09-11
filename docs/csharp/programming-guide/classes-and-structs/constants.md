---
title: Konstanten (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
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
ms.openlocfilehash: 85273420e9e0dbf4b8f24568d97be127c85d5f42
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="d922c-102">Konstanten (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d922c-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="d922c-103">Konstanten sind unveränderliche Werte, die zur Kompilierzeit bekannt sind und sich während der Lebensdauer des Programms nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d922c-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="d922c-104">Konstanten werden mit dem [const](../../../csharp/language-reference/keywords/const.md)-Modifizierer deklariert.</span><span class="sxs-lookup"><span data-stu-id="d922c-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="d922c-105">Nur die in C# integrierten Typen (außer <xref:System.Object?displayProperty=fullName>) können als `const` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d922c-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=fullName>) may be declared as `const`.</span></span> <span data-ttu-id="d922c-106">Eine Liste der integrierten Typen finden Sie unter [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="d922c-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="d922c-107">Benutzerdefinierte Typen einschließlich Klassen, Strukturen und Arrays können nicht `const` sein.</span><span class="sxs-lookup"><span data-stu-id="d922c-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="d922c-108">Verwenden Sie den [readonly](../../../csharp/language-reference/keywords/readonly.md)-Modifizierer zum Erstellen einer Klasse, einer Struktur oder eines Arrays, die/das zur Laufzeit einmal initialisiert wird (z.B. in einem Konstruktor) und danach nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d922c-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="d922c-109">C# unterstützt keine `const`-Methoden, -Eigenschaften oder -Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d922c-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="d922c-110">Der Enumerationstyp ermöglicht Ihnen das Definieren benannter Konstanten für ganzzahlige integrierte Typen (z.B. `int`, `uint`, `long` usw.).</span><span class="sxs-lookup"><span data-stu-id="d922c-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="d922c-111">Weitere Informationen finden Sie unter [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="d922c-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="d922c-112">Konstanten müssen initialisiert werden, wenn sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d922c-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="d922c-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d922c-113">For example:</span></span>  
  
 <span data-ttu-id="d922c-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d922c-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span></span>  
  
 <span data-ttu-id="d922c-115">In diesem Beispiel ist die Konstante `months` immer 12 und kann nicht einmal durch die Klasse selbst geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d922c-115">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="d922c-116">Wenn der Compiler einen konstanten Bezeichner im C#-Quellcode erkennt (z.B. `months`), ersetzt er den Literalwert direkt durch Code der Zwischensprache (Intermediate Language, IL), den er produziert.</span><span class="sxs-lookup"><span data-stu-id="d922c-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="d922c-117">Da zur Laufzeit keine Variablenadresse einer Konstanten zugeordnet ist, können `const`-Felder nicht durch Verweis übergeben werden und können nicht als l-Wert in einem Ausdruck stehen.</span><span class="sxs-lookup"><span data-stu-id="d922c-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d922c-118">Seien Sie vorsichtig beim Verweisen auf konstante Werte, die in anderem Code wie z.B. DLLs definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d922c-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="d922c-119">Wenn eine neue Version der DLL einen neuen Wert für die Konstante definiert, enthält das Programm weiterhin den alten Literalwert, bis es mit der neuen Version erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="d922c-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="d922c-120">Mehrere Konstanten desselben Typs können zur gleichen Zeit deklariert werden wie zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d922c-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 <span data-ttu-id="d922c-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d922c-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span></span>  
  
 <span data-ttu-id="d922c-122">Der Ausdruck, mit dem eine Konstante initialisiert wird, kann auf eine andere Konstante verweisen, wenn dadurch kein Zirkelverweis entsteht.</span><span class="sxs-lookup"><span data-stu-id="d922c-122">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="d922c-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d922c-123">For example:</span></span>  
  
 <span data-ttu-id="d922c-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d922c-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span></span>  
  
 <span data-ttu-id="d922c-125">Konstanten können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected internal` markiert werden.</span><span class="sxs-lookup"><span data-stu-id="d922c-125">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="d922c-126">Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf die Konstante zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d922c-126">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="d922c-127">Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d922c-127">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="d922c-128">Auf Konstanten wird zugegriffen, als wären sie [statische](../../../csharp/language-reference/keywords/static.md) Felder, da der Wert der Konstante für alle Instanzen des Typs identisch ist.</span><span class="sxs-lookup"><span data-stu-id="d922c-128">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="d922c-129">Sie verwenden nicht das `static`-Schlüsselwort, um sie zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d922c-129">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="d922c-130">Ausdrücke, die nicht in der Klasse enthalten sind, die die Konstante definiert, müssen den Klassennamen, einen Punkt und den Namen der Konstante verwenden, um auf die Konstante zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d922c-130">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="d922c-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d922c-131">For example:</span></span>  
  
 <span data-ttu-id="d922c-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d922c-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d922c-133">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d922c-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d922c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d922c-134">See Also</span></span>  
 <span data-ttu-id="d922c-135">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d922c-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d922c-136">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="d922c-136">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="d922c-137">[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="d922c-137">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="d922c-138">[Typen](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="d922c-138">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="d922c-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="d922c-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span></span>  
 [<span data-ttu-id="d922c-140">Immutability in C# Part One: Kinds of Immutability (Unveränderlichkeit in C# Teil eins: Arten von Unveränderlichkeit)</span><span class="sxs-lookup"><span data-stu-id="d922c-140">Immutability in C# Part One: Kinds of Immutability</span></span>](http://go.microsoft.com/fwlink/?LinkId=112379)

