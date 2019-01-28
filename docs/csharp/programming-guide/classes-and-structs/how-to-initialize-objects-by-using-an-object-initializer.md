---
title: 'Vorgehensweise: Initialisieren von Objekten mit einem Objektinitialisierer – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 2ac4242eb1bd24fd54cc1eca97acb96f39cc050b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607029"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="63f8a-102">Vorgehensweise: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="63f8a-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>

<span data-ttu-id="63f8a-103">Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="63f8a-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="63f8a-104">Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63f8a-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="63f8a-105">Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="63f8a-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="63f8a-106">Deshalb schlagen Objektinitialisierer, die öffentlichen Zugriff benötigen, fehl, wenn der Standardkonstruktor als `private` in der Klasse deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="63f8a-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="63f8a-107">Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="63f8a-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="63f8a-108">Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="63f8a-108">For more information, see [How to: Return Subsets of Element Properties in a Query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f8a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63f8a-109">Example</span></span>  

<span data-ttu-id="63f8a-110">Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="63f8a-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="63f8a-111">Dieses Beispiel legt Eigenschaften für den Typ `StudentName` fest:</span><span class="sxs-lookup"><span data-stu-id="63f8a-111">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp-interactive[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="63f8a-112">Objektinitialisierer können dafür verwendet werden, Indexer in einem Objekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="63f8a-112">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="63f8a-113">Das folgende Beispiel definiert eine `BaseballTeam`-Klasse, die einen Indexer verwendet, um Player an verschiedenen Positionen abzurufen und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="63f8a-113">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="63f8a-114">Der Initialisierer kann Player auf Grundlage der Abkürzung für die Position oder der Zahl, die für jede einzelne Position auf einem Baseball-Scoresheet verwendet wird, zuweisen:</span><span class="sxs-lookup"><span data-stu-id="63f8a-114">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp-interactive[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="63f8a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63f8a-115">See also</span></span>

- [<span data-ttu-id="63f8a-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="63f8a-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="63f8a-117">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="63f8a-117">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
