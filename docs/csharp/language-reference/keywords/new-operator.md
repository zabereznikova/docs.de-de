---
title: new-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 409a5307eaacd2eac865e2882cc7228521260dbe
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421872"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="99938-102">new-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="99938-102">new operator (C# Reference)</span></span>

<span data-ttu-id="99938-103">Wird zum Erstellen von Objekten und zum Aufrufen von Konstruktoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="99938-103">Used to create objects and invoke constructors.</span></span> <span data-ttu-id="99938-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="99938-104">For example:</span></span>

```csharp
Class1 obj  = new Class1();
```

<span data-ttu-id="99938-105">Er wird auch verwendet, um Instanzen von anonymen Typen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="99938-105">It is also used to create instances of anonymous types:</span></span>

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

<span data-ttu-id="99938-106">Der Operator `new` wird auch verwendet, um den parameterlosen Konstruktor für Werttypen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="99938-106">The `new` operator is also used to invoke the parameterless constructor for value types.</span></span> <span data-ttu-id="99938-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="99938-107">For example:</span></span>

```csharp
int i = new int();
```

<span data-ttu-id="99938-108">In der vorherigen Anweisung wird `i` auf `0` initialisiert, dem Standardwert für den `int`-Typ.</span><span class="sxs-lookup"><span data-stu-id="99938-108">In the preceding statement, `i` is initialized to `0`, which is the default value for the type `int`.</span></span> <span data-ttu-id="99938-109">Die Anweisung hat den gleichen Effekt wie die Folgende:</span><span class="sxs-lookup"><span data-stu-id="99938-109">The statement has the same effect as the following:</span></span>

```csharp
int i = 0;
```

<span data-ttu-id="99938-110">Eine vollständige Liste der Standardwerte finden Sie in der [Tabelle für Standardwerte](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="99938-110">For a complete list of default values, see [Default Values Table](default-values-table.md).</span></span>

<span data-ttu-id="99938-111">Beachten Sie, dass das Deklarieren eines parameterlosen Konstruktors für eine [Struktur](struct.md) ein Fehler ist, da jeder Werttyp implizit einen öffentlichen parameterlosen Konstruktor besitzt.</span><span class="sxs-lookup"><span data-stu-id="99938-111">Remember that it is an error to declare a parameterless constructor for a [struct](struct.md) because every value type implicitly has a public parameterless constructor.</span></span> <span data-ttu-id="99938-112">Es ist möglich, parametrisierte Konstruktoren auf einem Strukturtyp zu deklarieren, um seine Standardwerte festzulegen. Dies ist aber nur notwendig, wenn andere Werte als der Standardwert erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="99938-112">It is possible to declare parameterized constructors on a struct type to set its initial values, but this is only necessary if values other than the default are required.</span></span>

<span data-ttu-id="99938-113">Werttypobjekte wie Strukturen und Verweistypobjekte wie Klassen werden automatisch zerstört. Werttypobjekte werden jedoch zerstört, wenn der sie enthaltende Kontext zerstört wird, während Verweistypobjekte zu einem unbestimmten Zeitpunkt nach dem Entfernen der letzten Verweise auf diese Dateien durch die Garbage Collection zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="99938-113">Both value-type objects such as structs and reference-type objects such as classes are destroyed automatically, but value-type objects are destroyed when their containing context is destroyed, whereas reference-type objects are destroyed by the garbage collector at an unspecified time after the last reference to them is removed.</span></span> <span data-ttu-id="99938-114">Bei Typen, die Ressourcen wie Dateihandles oder Netzwerkverbindungen enthalten, ist eine deterministische Bereinigung empfehlenswert, um sicherzustellen, dass die darin enthaltenen Ressourcen so bald wie möglich freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="99938-114">For types that contain resources such as file handles, or network connections, it is desirable to employ deterministic cleanup to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="99938-115">Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="99938-115">For more information, see [using Statement](using-statement.md).</span></span>

<span data-ttu-id="99938-116">Operator `new` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="99938-116">The `new` operator cannot be overloaded.</span></span>

<span data-ttu-id="99938-117">Wenn der `new`-Operator bei der Zuweisung von Arbeitsspeicher scheitert, löst er die Ausnahme <xref:System.OutOfMemoryException> aus.</span><span class="sxs-lookup"><span data-stu-id="99938-117">If the `new` operator fails to allocate memory, it throws the exception, <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="99938-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99938-118">Example</span></span>

<span data-ttu-id="99938-119">Im folgenden Beispiel werden ein `struct`-Objekt und ein Klassenobjekt mithilfe des `new`-Operators erstellt und initialisiert. Anschließend werden ihnen Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="99938-119">In the following example, a `struct` object and a class object are created and initialized by using the `new` operator and then assigned values.</span></span> <span data-ttu-id="99938-120">Die Standardwerte und die zugewiesenen Werte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99938-120">The default and the assigned values are displayed.</span></span>

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

<span data-ttu-id="99938-121">Beachten Sie im Beispiel, dass der Standardwert einer Zeichenfolge `null` ist.</span><span class="sxs-lookup"><span data-stu-id="99938-121">Notice in the example that the default value of a string is `null`.</span></span> <span data-ttu-id="99938-122">Daher wird er nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99938-122">Therefore, it is not displayed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="99938-123">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="99938-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="99938-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99938-124">See also</span></span>

- [<span data-ttu-id="99938-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="99938-125">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="99938-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="99938-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="99938-127">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="99938-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="99938-128">new</span><span class="sxs-lookup"><span data-stu-id="99938-128">new</span></span>](new.md)
- [<span data-ttu-id="99938-129">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="99938-129">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
