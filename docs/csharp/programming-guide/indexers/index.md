---
title: 'Indexer – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 03/10/2017
f1_keywords:
  - cs.indexers
helpviewer_keywords:
  - 'indexers [C#]'
  - 'C# language, indexers'
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="4d5c5-102">Indexer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4d5c5-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="4d5c5-103">Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="4d5c5-104">Der indizierte Wert kann festgelegt oder ohne explizite Angabe eines Typs oder Instanzmembers abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="4d5c5-105">Indexer ähneln [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md). Der Unterschied besteht jedoch darin, dass ihre Zugriffsmethoden Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="4d5c5-106">Im folgenden Beispiel wird eine generische Klasse mit einfachen [get](../../../csharp/language-reference/keywords/get.md)- und [set](../../../csharp/language-reference/keywords/set.md)-Accessormethoden zum Zuweisen und Abrufen von Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="4d5c5-107">Die `Program`-Klasse erstellt eine Instanz dieser Klasse für das Speichern von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="4d5c5-108">Weitere Beispiele finden Sie unter [Verwandte Abschnitte](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="4d5c5-108">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="4d5c5-109">Ausdruckstextdefinitionen</span><span class="sxs-lookup"><span data-stu-id="4d5c5-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="4d5c5-110">Get- oder Set-Accessoren eines Indexers bestehen häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt oder festlegt.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="4d5c5-111">Ausdruckskörpermember bieten eine vereinfachte Syntax zur Unterstützung dieses Szenarios.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="4d5c5-112">Ab C# 6 kann ein schreibgeschützter Indexer als Ausdruckskörpermember implementiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="4d5c5-113">Beachten Sie, dass `=>` den Ausdruckstext vorstellt und dass das `get`-Schlüsselwort nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="4d5c5-114">Ab C# 7.0 können die Get- und die Set-Zugriffsmethode als Ausdruckskörpermember implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="4d5c5-115">In diesem Fall müssen die Schlüsselwörter `get` und `set` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="4d5c5-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4d5c5-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="4d5c5-117">Übersicht über Indexer</span><span class="sxs-lookup"><span data-stu-id="4d5c5-117">Indexers Overview</span></span>  
  
-   <span data-ttu-id="4d5c5-118">Indexer ermöglichen es Objekten, in ähnlicher Weise wie Arrays indiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="4d5c5-119">Ein `get`-Accessor gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="4d5c5-120">Ein `set`-Accessor weist einen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-120">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="4d5c5-121">Das [this](../../../csharp/language-reference/keywords/this.md)-Schlüsselwort wird zum Definieren des Indexers verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-121">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="4d5c5-122">Das [value](../../../csharp/language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Indexer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-122">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="4d5c5-123">Indexer müssen nicht durch einen Ganzzahlwert indiziert werden. Sie können entscheiden, wie Sie den spezifischen Suchmechanismus definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="4d5c5-124">Indexer können überladen werden.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-124">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="4d5c5-125">Indexer können mehr als einen formalen Parameter aufweisen, beispielsweise beim Zugreifen auf ein 2D-Array.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <a name="BKMK_RelatedSections"></a> <span data-ttu-id="4d5c5-126">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4d5c5-126">Related Sections</span></span>  
  
-   [<span data-ttu-id="4d5c5-127">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="4d5c5-127">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="4d5c5-128">Indexer in Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4d5c5-128">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="4d5c5-129">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="4d5c5-129">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="4d5c5-130">Einschränken des Zugriffsmethodenzugriffs</span><span class="sxs-lookup"><span data-stu-id="4d5c5-130">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="4d5c5-131">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4d5c5-131">C# Language Specification</span></span>  

<span data-ttu-id="4d5c5-132">Weitere Informationen erhalten Sie unter [Indexer](~/_csharplang/spec/classes.md#indexers) in der [C#-Sprachspezifikation](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d5c5-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="4d5c5-133">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="4d5c5-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d5c5-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d5c5-134">See also</span></span>

- [<span data-ttu-id="4d5c5-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4d5c5-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4d5c5-136">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4d5c5-136">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
