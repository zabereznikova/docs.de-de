---
title: new-Operator (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
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
ms.openlocfilehash: 59e1cc2006548df9a7a10283a34044040e5c2fef
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="new-operator-c-reference"></a><span data-ttu-id="e9e2d-102">new-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e9e2d-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="e9e2d-103">Wird zum Erstellen von Objekten und zum Aufrufen von Konstruktoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="e9e2d-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="e9e2d-105">Er wird auch verwendet, um Instanzen von anonymen Typen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="e9e2d-106">Der `new`-Operator wird auch verwendet, um den Standardkonstruktor für Werttypen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="e9e2d-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="e9e2d-108">In der vorherigen Anweisung wird `i` auf `0` initialisiert, dem Standardwert für den `int`-Typ.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="e9e2d-109">Die Anweisung hat den gleichen Effekt wie die Folgende:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="e9e2d-110">Eine vollständige Liste der Standardwerte finden Sie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="e9e2d-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="e9e2d-111">Beachten Sie, dass das Deklarieren eines Standardkonstruktors für eine [Struktur](../../../csharp/language-reference/keywords/struct.md) ein Fehler ist, da jeder Werttyp implizit einen öffentlichen Standardkonstruktor besitzt.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="e9e2d-112">Es ist möglich, parametrisierte Konstruktoren auf einem Strukturtyp zu deklarieren, um seine Standardwerte festzulegen. Dies ist aber nur notwendig, wenn andere Werte als der Standardwert erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="e9e2d-113">Werttypobjekte wie Strukturen werden auf einem Stapel erstellt, während Verweistypobjekte auf einem Heap erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="e9e2d-114">Beide Objekttypen werden automatisch zerstört. Allerdings werden auf Werttypen basierende Objekte zerstört, wenn sie den gültigen Bereich verlassen. Auf Verweistypen basierende Objekte hingegen werden zu einem unbestimmten Zeitpunkt zerstört, nachdem der letzte Verweis auf sie entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="e9e2d-115">Für Verweistypen, die feste Ressourcen wie große Mengen an Speicher, Dateihandles oder Netzwerkverbindungen verbrauchen, ist es manchmal wünschenswert, einen deterministischen Abschluss zu nutzen, um sicherzustellen, dass das Objekt sobald wie möglich zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="e9e2d-116">Weitere Informationen finden Sie unter [using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e9e2d-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="e9e2d-117">Der Operator `new` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="e9e2d-118">Wenn der `new`-Operator bei der Zuweisung von Arbeitsspeicher scheitert, löst er die Ausnahme <xref:System.OutOfMemoryException> aus.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9e2d-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e9e2d-119">Example</span></span>  
 <span data-ttu-id="e9e2d-120">Im folgenden Beispiel werden ein `struct`-Objekt und ein Klassenobjekt mithilfe des `new`-Operators erstellt und initialisiert. Anschließend werden ihnen Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="e9e2d-121">Die Standardwerte und die zugewiesenen Werte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-121">The default and the assigned values are displayed.</span></span>  
  
 <span data-ttu-id="e9e2d-122">[!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9e2d-122">[!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="e9e2d-123">Beachten Sie im Beispiel, dass der Standardwert einer Zeichenfolge `null` ist.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-123">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="e9e2d-124">Daher wird er nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-124">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e9e2d-125">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e9e2d-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9e2d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9e2d-126">See Also</span></span>  
 <span data-ttu-id="e9e2d-127">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9e2d-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e9e2d-128">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9e2d-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e9e2d-129">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9e2d-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e9e2d-130">[Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="e9e2d-130">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="e9e2d-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="e9e2d-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="e9e2d-132">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="e9e2d-132">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

