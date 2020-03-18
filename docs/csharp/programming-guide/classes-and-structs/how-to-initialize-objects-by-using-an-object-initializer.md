---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer – C#-Programmierhandbuch'
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: a2ecc9df211d0082bd4b413653e374758c877abc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705586"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="189f6-102">Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="189f6-102">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="189f6-103">Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="189f6-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="189f6-104">Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="189f6-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="189f6-105">Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="189f6-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="189f6-106">Daher tritt bei Objektinitialisierern, die öffentlichen Zugriff benötigen, ein Fehler auf, wenn der parameterlose Konstruktor in der Klasse als `private` deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="189f6-106">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="189f6-107">Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="189f6-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="189f6-108">Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="189f6-108">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="189f6-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="189f6-109">Example</span></span>  

<span data-ttu-id="189f6-110">Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="189f6-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="189f6-111">Dieses Beispiel legt Eigenschaften für den Typ `StudentName` fest:</span><span class="sxs-lookup"><span data-stu-id="189f6-111">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="189f6-112">Objektinitialisierer können dafür verwendet werden, Indexer in einem Objekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="189f6-112">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="189f6-113">Das folgende Beispiel definiert eine `BaseballTeam`-Klasse, die einen Indexer verwendet, um Player an verschiedenen Positionen abzurufen und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="189f6-113">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="189f6-114">Der Initialisierer kann Player auf Grundlage der Abkürzung für die Position oder der Zahl, die für jede einzelne Position auf einem Baseball-Scoresheet verwendet wird, zuweisen:</span><span class="sxs-lookup"><span data-stu-id="189f6-114">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="189f6-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="189f6-115">See also</span></span>

- [<span data-ttu-id="189f6-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="189f6-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="189f6-117">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="189f6-117">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
