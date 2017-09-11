---
title: Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6baf985e8031e1e859d20570168222ca8f368eff
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="77cb1-102">Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="77cb1-102">Explicit Interface Implementation (C# Programming Guide)</span></span>
<span data-ttu-id="77cb1-103">Wenn eine [Klasse](../../../csharp/language-reference/keywords/class.md) zwei Schnittstellen implementiert, die einen Member mit derselben Signatur enthalten, bewirkt die Implementierung dieses Members in der Klasse, dass beide Schnittstellen diesen Member als ihre Implementierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="77cb1-103">If a [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="77cb1-104">Im folgenden Beispiel rufen alle Aufrufe von `Paint` dieselbe Methode auf.</span><span class="sxs-lookup"><span data-stu-id="77cb1-104">In the following example, all the calls to `Paint` invoke the same method.</span></span>  
  
 <span data-ttu-id="77cb1-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="77cb1-105">[!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]</span></span>  
  
 <span data-ttu-id="77cb1-106">Falls die beiden [Schnittstellen](../../../csharp/language-reference/keywords/interface.md)-Member jedoch nicht dieselbe Funktion erfüllen, kann dies zu einer falschen Implementierung von einer oder beiden Schnittstellen führen.</span><span class="sxs-lookup"><span data-stu-id="77cb1-106">If the two [interface](../../../csharp/language-reference/keywords/interface.md) members do not perform the same function, however, this can lead to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="77cb1-107">Es ist möglich, einen Schnittstellenmember explizit zu implementieren, also einen Klassenmember zu erstellen, der nur über die Schnittstelle aufgerufen wird und für diese Schnittstelle spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="77cb1-107">It is possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="77cb1-108">Dazu benennt man den Klassenmember mit dem Namen der Schnittstelle und einem Punkt.</span><span class="sxs-lookup"><span data-stu-id="77cb1-108">This is accomplished by naming the class member with the name of the interface and a period.</span></span> <span data-ttu-id="77cb1-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="77cb1-109">For example:</span></span>  
  
 <span data-ttu-id="77cb1-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="77cb1-110">[!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]</span></span>  
  
 <span data-ttu-id="77cb1-111">Der Klassenmember `IControl.Paint` ist nur über die Schnittstelle `IControl` verfügbar, und `ISurface.Paint` ist nur über `ISurface` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77cb1-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="77cb1-112">Beide Methodenimplementierungen sind getrennt, und keine ist direkt in der Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="77cb1-112">Both method implementations are separate, and neither is available directly on the class.</span></span> <span data-ttu-id="77cb1-113">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="77cb1-113">For example:</span></span>  
  
 <span data-ttu-id="77cb1-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="77cb1-114">[!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]</span></span>  
  
 <span data-ttu-id="77cb1-115">Explizite Implementierung wird auch zum Lösen von Konflikten verwendet, bei denen zwei Schnittstellen verschiedene Member mit demselben Namen deklarieren, z.B. eine Eigenschaft und eine Methode:</span><span class="sxs-lookup"><span data-stu-id="77cb1-115">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method:</span></span>  
  
 <span data-ttu-id="77cb1-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="77cb1-116">[!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]</span></span>  
  
 <span data-ttu-id="77cb1-117">Um beide Schnittstellen zu implementieren, muss eine Klasse zur Vermeidung eines Compilerfehlers die explizite Implementierung entweder für Eigenschaft P, für Methode P oder für beide verwenden.</span><span class="sxs-lookup"><span data-stu-id="77cb1-117">To implement both interfaces, a class has to use explicit implementation either for the property P, or the method P, or both, to avoid a compiler error.</span></span> <span data-ttu-id="77cb1-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="77cb1-118">For example:</span></span>  
  
 <span data-ttu-id="77cb1-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="77cb1-119">[!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77cb1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77cb1-120">See Also</span></span>  
 <span data-ttu-id="77cb1-121">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="77cb1-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="77cb1-122">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="77cb1-122">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="77cb1-123">[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="77cb1-123">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="77cb1-124">Vererbung</span><span class="sxs-lookup"><span data-stu-id="77cb1-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

