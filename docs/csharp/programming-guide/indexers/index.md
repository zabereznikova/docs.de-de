---
title: Indexer – C#-Programmierhandbuch
description: Mithilfe von Indexern in C# können Klassen- oder Strukturinstanzen wie Arrays indiziert werden. Sie können den indizierten Wert festlegen oder abrufen, ohne einen Typ oder Instanzmember anzugeben.
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: ea95eef7bb9ba232e4d59e3f833b82e98398fc33
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495303"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="cfc10-104">Indexer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cfc10-104">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="cfc10-105">Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-105">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="cfc10-106">Der indizierte Wert kann festgelegt oder ohne explizite Angabe eines Typs oder Instanzmembers abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-106">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="cfc10-107">Indexer ähneln [Eigenschaften](../classes-and-structs/properties.md). Der Unterschied besteht jedoch darin, dass ihre Zugriffsmethoden Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-107">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="cfc10-108">Im folgenden Beispiel wird eine generische Klasse mit einfachen [get](../../language-reference/keywords/get.md)- und [set](../../language-reference/keywords/set.md)-Accessormethoden zum Zuweisen und Abrufen von Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="cfc10-108">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="cfc10-109">Die `Program`-Klasse erstellt eine Instanz dieser Klasse für das Speichern von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="cfc10-109">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="cfc10-110">Weitere Beispiele finden Sie unter [Verwandte Abschnitte](./index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="cfc10-110">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="cfc10-111">Ausdruckstextdefinitionen</span><span class="sxs-lookup"><span data-stu-id="cfc10-111">Expression Body Definitions</span></span>  

<span data-ttu-id="cfc10-112">Get- oder Set-Accessoren eines Indexers bestehen häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt oder festlegt.</span><span class="sxs-lookup"><span data-stu-id="cfc10-112">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="cfc10-113">Ausdruckskörpermember bieten eine vereinfachte Syntax zur Unterstützung dieses Szenarios.</span><span class="sxs-lookup"><span data-stu-id="cfc10-113">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="cfc10-114">Ab C# 6 kann ein schreibgeschützter Indexer als Ausdruckskörpermember implementiert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cfc10-114">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="cfc10-115">Beachten Sie, dass `=>` den Ausdruckstext vorstellt und dass das `get`-Schlüsselwort nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfc10-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span>

<span data-ttu-id="cfc10-116">Ab C# 7.0 können die Get- und die Set-Zugriffsmethode als Ausdruckskörpermember implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-116">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="cfc10-117">In diesem Fall müssen die Schlüsselwörter `get` und `set` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="cfc10-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cfc10-118">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="cfc10-119">Übersicht über Indexer</span><span class="sxs-lookup"><span data-stu-id="cfc10-119">Indexers Overview</span></span>  
  
- <span data-ttu-id="cfc10-120">Indexer ermöglichen es Objekten, in ähnlicher Weise wie Arrays indiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-120">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="cfc10-121">Ein `get`-Accessor gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="cfc10-121">A `get` accessor returns a value.</span></span> <span data-ttu-id="cfc10-122">Ein `set`-Accessor weist einen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="cfc10-122">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="cfc10-123">Das [this](../../language-reference/keywords/this.md)-Schlüsselwort wird zum Definieren des Indexers verwendet.</span><span class="sxs-lookup"><span data-stu-id="cfc10-123">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="cfc10-124">Das [value](../../language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Accessor zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="cfc10-124">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
  
- <span data-ttu-id="cfc10-125">Indexer müssen nicht durch einen Ganzzahlwert indiziert werden. Sie können entscheiden, wie Sie den spezifischen Suchmechanismus definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="cfc10-125">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="cfc10-126">Indexer können überladen werden.</span><span class="sxs-lookup"><span data-stu-id="cfc10-126">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="cfc10-127">Indexer können mehr als einen formalen Parameter aufweisen, beispielsweise beim Zugreifen auf ein 2D-Array.</span><span class="sxs-lookup"><span data-stu-id="cfc10-127">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> <span data-ttu-id="cfc10-128">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cfc10-128">Related Sections</span></span>  
  
- [<span data-ttu-id="cfc10-129">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="cfc10-129">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="cfc10-130">Indexer in Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cfc10-130">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="cfc10-131">Vergleich zwischen Eigenschaften und Indexern</span><span class="sxs-lookup"><span data-stu-id="cfc10-131">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="cfc10-132">Einschränken des Zugriffsmethodenzugriffs</span><span class="sxs-lookup"><span data-stu-id="cfc10-132">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="cfc10-133">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="cfc10-133">C# Language Specification</span></span>  

<span data-ttu-id="cfc10-134">Weitere Informationen erhalten Sie unter [Indexer](~/_csharplang/spec/classes.md#indexers) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="cfc10-134">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="cfc10-135">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="cfc10-135">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cfc10-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfc10-136">See also</span></span>

- [<span data-ttu-id="cfc10-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cfc10-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cfc10-138">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cfc10-138">Properties</span></span>](../classes-and-structs/properties.md)
