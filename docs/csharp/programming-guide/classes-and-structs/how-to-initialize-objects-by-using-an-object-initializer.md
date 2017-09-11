---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
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
ms.openlocfilehash: 01f2391680d9236b42f0d015b944b8f12455d0c8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="89c56-102">Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="89c56-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="89c56-103">Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="89c56-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="89c56-104">Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89c56-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="89c56-105">Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="89c56-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="89c56-106">Deshalb schlagen Objektinitialisierer, die öffentlichen Zugriff benötigen, fehl, wenn der Standardkonstruktor als `private` in der Klasse deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="89c56-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="89c56-107">Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="89c56-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="89c56-108">Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="89c56-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89c56-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89c56-109">Example</span></span>  
 <span data-ttu-id="89c56-110">Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="89c56-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 <span data-ttu-id="89c56-111">[!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="89c56-111">[!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="89c56-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89c56-112">Example</span></span>  
 <span data-ttu-id="89c56-113">Im folgenden Beispiel wird das Initialisieren einer Reihe von `StudentName`-Typen mithilfe eines Auflistungsinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="89c56-113">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="89c56-114">Beachten Sie, dass ein Auflistungsinitialisierer aus einer Reihe von durch Trennzeichen getrennten Objektinitialisierern besteht.</span><span class="sxs-lookup"><span data-stu-id="89c56-114">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 <span data-ttu-id="89c56-115">[!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="89c56-115">[!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89c56-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="89c56-116">Compiling the Code</span></span>  
 <span data-ttu-id="89c56-117">Um diesen Code auszuführen, kopieren Sie die Klasse, und fügen Sie sie in ein Visual C#-Konsolenanwendungsprojekt ein, das in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="89c56-117">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="89c56-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89c56-118">See Also</span></span>  
 <span data-ttu-id="89c56-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="89c56-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="89c56-120">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="89c56-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

