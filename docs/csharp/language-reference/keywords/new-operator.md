---
title: new-Operator (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3c2b484b9872a54ce42520de77a723b9edb441a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="893f5-102">new-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="893f5-102">new Operator (C# Reference)</span></span>
<span data-ttu-id="893f5-103">Wird zum Erstellen von Objekten und zum Aufrufen von Konstruktoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="893f5-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="893f5-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="893f5-104">For example:</span></span>  
  
```  
Class1 obj  = new Class1();  
```  
  
 <span data-ttu-id="893f5-105">Er wird auch verwendet, um Instanzen von anonymen Typen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="893f5-105">It is also used to create instances of anonymous types:</span></span>  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 <span data-ttu-id="893f5-106">Der `new`-Operator wird auch verwendet, um den Standardkonstruktor für Werttypen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="893f5-106">The `new` operator is also used to invoke the default constructor for value types.</span></span> <span data-ttu-id="893f5-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="893f5-107">For example:</span></span>  
  
```  
int i = new int();  
```  
  
 <span data-ttu-id="893f5-108">In der vorherigen Anweisung wird `i` auf `0` initialisiert, dem Standardwert für den `int`-Typ.</span><span class="sxs-lookup"><span data-stu-id="893f5-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="893f5-109">Die Anweisung hat den gleichen Effekt wie die Folgende:</span><span class="sxs-lookup"><span data-stu-id="893f5-109">The statement has the same effect as the following:</span></span>  
  
```  
int i = 0;  
```  
  
 <span data-ttu-id="893f5-110">Eine vollständige Liste der Standardwerte finden Sie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="893f5-110">For a complete list of default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="893f5-111">Beachten Sie, dass das Deklarieren eines Standardkonstruktors für eine [Struktur](../../../csharp/language-reference/keywords/struct.md) ein Fehler ist, da jeder Werttyp implizit einen öffentlichen Standardkonstruktor besitzt.</span><span class="sxs-lookup"><span data-stu-id="893f5-111">Remember that it is an error to declare a default constructor for a [struct](../../../csharp/language-reference/keywords/struct.md) because every value type implicitly has a public default constructor.</span></span> <span data-ttu-id="893f5-112">Es ist möglich, parametrisierte Konstruktoren auf einem Strukturtyp zu deklarieren, um seine Standardwerte festzulegen. Dies ist aber nur notwendig, wenn andere Werte als der Standardwert erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="893f5-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>  
  
 <span data-ttu-id="893f5-113">Werttypobjekte wie Strukturen werden auf einem Stapel erstellt, während Verweistypobjekte auf einem Heap erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="893f5-113">Value-type objects such as structs are created on the stack, while reference-type objects such as classes are created on the heap.</span></span> <span data-ttu-id="893f5-114">Beide Objekttypen werden automatisch zerstört. Allerdings werden auf Werttypen basierende Objekte zerstört, wenn sie den gültigen Bereich verlassen. Auf Verweistypen basierende Objekte hingegen werden zu einem unbestimmten Zeitpunkt zerstört, nachdem der letzte Verweis auf sie entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="893f5-114">Both types of objects are destroyed automatically, but objects based on value types are destroyed when they go out of scope, whereas objects based on reference types are destroyed at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="893f5-115">Für Verweistypen, die feste Ressourcen wie große Mengen an Speicher, Dateihandles oder Netzwerkverbindungen verbrauchen, ist es manchmal wünschenswert, einen deterministischen Abschluss zu nutzen, um sicherzustellen, dass das Objekt sobald wie möglich zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="893f5-115">For reference types that consume fixed resources such as large amounts of memory, file handles, or network connections, it is sometimes desirable to employ deterministic finalization to ensure that the object is destroyed as soon as possible.</span></span> <span data-ttu-id="893f5-116">Weitere Informationen finden Sie unter [using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="893f5-116">For more information, see [using Statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span>  
  
 <span data-ttu-id="893f5-117">Operator `new` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="893f5-117">The `new` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="893f5-118">Wenn der `new`-Operator bei der Zuweisung von Arbeitsspeicher scheitert, löst er die Ausnahme <xref:System.OutOfMemoryException> aus.</span><span class="sxs-lookup"><span data-stu-id="893f5-118">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="893f5-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="893f5-119">Example</span></span>  
 <span data-ttu-id="893f5-120">Im folgenden Beispiel werden ein `struct`-Objekt und ein Klassenobjekt mithilfe des `new`-Operators erstellt und initialisiert. Anschließend werden ihnen Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="893f5-120">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="893f5-121">Die Standardwerte und die zugewiesenen Werte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="893f5-121">The default and the assigned values are displayed.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 <span data-ttu-id="893f5-122">Beachten Sie im Beispiel, dass der Standardwert einer Zeichenfolge `null` ist.</span><span class="sxs-lookup"><span data-stu-id="893f5-122">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="893f5-123">Daher wird er nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="893f5-123">Therefore, it is not displayed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="893f5-124">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="893f5-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="893f5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="893f5-125">See Also</span></span>  
 [<span data-ttu-id="893f5-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="893f5-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="893f5-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="893f5-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="893f5-128">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="893f5-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="893f5-129">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="893f5-129">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="893f5-130">new</span><span class="sxs-lookup"><span data-stu-id="893f5-130">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="893f5-131">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="893f5-131">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
