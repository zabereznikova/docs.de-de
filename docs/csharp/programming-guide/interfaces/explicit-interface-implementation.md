---
title: Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: 7494f7d6a3897d56419f9d3aa96668fd9dab5f35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="c7da1-102">Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c7da1-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="c7da1-103">Wenn eine [Klasse](../../../csharp/language-reference/keywords/class.md) zwei Schnittstellen implementiert, die einen Member mit derselben Signatur enthalten, bewirkt die Implementierung dieses Members in der Klasse, dass beide Schnittstellen diesen Member als ihre Implementierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7da1-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="c7da1-104">Im folgenden Beispiel rufen alle Aufrufe von `Paint` dieselbe Methode auf.</span><span class="sxs-lookup"><span data-stu-id="c7da1-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 <span data-ttu-id="c7da1-105">Falls die beiden [Schnittstellen](../../../csharp/language-reference/keywords/interface.md)-Member jedoch nicht dieselbe Funktion erfüllen, kann dies zu einer falschen Implementierung von einer oder beiden Schnittstellen führen.</span><span class="sxs-lookup"><span data-stu-id="c7da1-105">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="c7da1-106">Es ist möglich, einen Schnittstellenmember explizit zu implementieren, also einen Klassenmember zu erstellen, der nur über die Schnittstelle aufgerufen wird und für diese Schnittstelle spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="c7da1-106">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="c7da1-107">Dazu benennt man den Klassenmember mit dem Namen der Schnittstelle und einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="c7da1-107">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="c7da1-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c7da1-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 <span data-ttu-id="c7da1-109">Der Klassenmember `IControl.Paint` ist nur über die Schnittstelle `IControl` verfügbar, und `ISurface.Paint` ist nur über `ISurface` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7da1-109">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="c7da1-110">Beide Methodenimplementierungen sind getrennt, und keine ist direkt in der Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7da1-110">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="c7da1-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c7da1-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 <span data-ttu-id="c7da1-112">Explizite Implementierung wird auch zum Lösen von Konflikten verwendet, bei denen zwei Schnittstellen verschiedene Member mit demselben Namen deklarieren, z.B. eine Eigenschaft und eine Methode:</span><span class="sxs-lookup"><span data-stu-id="c7da1-112">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 <span data-ttu-id="c7da1-113">Um beide Schnittstellen zu implementieren, muss eine Klasse zur Vermeidung eines Compilerfehlers die explizite Implementierung entweder für Eigenschaft P, für Methode P oder für beide verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7da1-113">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="c7da1-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c7da1-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c7da1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7da1-115">See Also</span></span>  
 [<span data-ttu-id="c7da1-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c7da1-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c7da1-117">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="c7da1-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="c7da1-118">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c7da1-118">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="c7da1-119">Vererbung</span><span class="sxs-lookup"><span data-stu-id="c7da1-119">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
