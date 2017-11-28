---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d1e65f8519062f6bceeb466a3b72c5719c0918f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="b1ebd-102">Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b1ebd-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="b1ebd-103">Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="b1ebd-104">Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="b1ebd-105">Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="b1ebd-106">Deshalb schlagen Objektinitialisierer, die öffentlichen Zugriff benötigen, fehl, wenn der Standardkonstruktor als `private` in der Klasse deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="b1ebd-107">Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="b1ebd-108">Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="b1ebd-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1ebd-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1ebd-109">Example</span></span>  
 <span data-ttu-id="b1ebd-110">Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="b1ebd-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1ebd-111">Example</span></span>  
 <span data-ttu-id="b1ebd-112">Im folgenden Beispiel wird das Initialisieren einer Reihe von `StudentName`-Typen mithilfe eines Auflistungsinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-112">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="b1ebd-113">Beachten Sie, dass ein Auflistungsinitialisierer aus einer Reihe von durch Trennzeichen getrennten Objektinitialisierern besteht.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-113">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1ebd-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b1ebd-114">Compiling the Code</span></span>  
 <span data-ttu-id="b1ebd-115">Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b1ebd-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ebd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1ebd-116">See Also</span></span>  
 [<span data-ttu-id="b1ebd-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b1ebd-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b1ebd-118">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="b1ebd-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
