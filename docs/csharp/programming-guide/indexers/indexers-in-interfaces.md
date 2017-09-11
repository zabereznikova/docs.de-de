---
title: Indexer in Schnittstellen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
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
ms.openlocfilehash: 2715602dadea40324f613bb07b5dd332ed18c25c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="f8d8d-102">Indexer in Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f8d8d-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="f8d8d-103">Indexer können für eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="f8d8d-104">Accessoren für Schnittstellenindexer unterscheiden sich von den Accessoren für [Klassen](../../../csharp/language-reference/keywords/class.md)-Indexer in den folgenden Punkten:</span><span class="sxs-lookup"><span data-stu-id="f8d8d-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="f8d8d-105">Schnittstellenaccessoren verwenden keine Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="f8d8d-106">Ein Schnittstellenaccessor enthält keinen Text.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="f8d8d-107">Der Zweck eines Accessors besteht darin anzugeben, ob der Indexer gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="f8d8d-108">Das folgende Beispiel zeigt den Accessor für einen Schnittstellenindexer:</span><span class="sxs-lookup"><span data-stu-id="f8d8d-108">The following is an example of an interface indexer accessor:</span></span>  
  
 <span data-ttu-id="f8d8d-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8d8d-109">[!code-cs[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="f8d8d-110">Die Signatur eines Indexers muss sich von den Signaturen aller anderen in derselben Schnittstelle deklarierten Indexer unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-110">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d8d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8d8d-111">Example</span></span>  
 <span data-ttu-id="f8d8d-112">Das folgende Beispiel zeigt, wie Schnittstellenindexer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-112">The following example shows how to implement interface indexers.</span></span>  
  
 <span data-ttu-id="f8d8d-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8d8d-113">[!code-cs[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="f8d8d-114">Im vorherigen Beispiel könnte der Schnittstellenmember durch Verwendung des vollqualifizierten Namens des Schnittstellenmembers explizit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="f8d8d-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8d8d-115">For example:</span></span>  
  
```  
public string ISomeInterface.this   
{   
}   
```  
  
 <span data-ttu-id="f8d8d-116">Der vollqualifizierte Name ist jedoch nur erforderlich, um Mehrdeutigkeiten zu vermeiden, wenn mehr als eine Schnittstelle mit derselben Indexersignatur von der Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="f8d8d-117">Wenn z.B. eine `Employee`-Klasse die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen dieselbe Indexersignatur besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="f8d8d-118">Das bedeutet, dass die folgende Indexerdeklaration:</span><span class="sxs-lookup"><span data-stu-id="f8d8d-118">That is, the following indexer declaration:</span></span>  
  
```  
public string IEmployee.this   
{   
}   
```  
  
 <span data-ttu-id="f8d8d-119">den Indexer für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="f8d8d-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
public string ICitizen.this   
{   
}   
```  
  
 <span data-ttu-id="f8d8d-120">den Indexer für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="f8d8d-120">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d8d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8d8d-121">See Also</span></span>  
 <span data-ttu-id="f8d8d-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8d8d-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f8d8d-123">[Indexer](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8d8d-123">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="f8d8d-124">[Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="f8d8d-124">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="f8d8d-125">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f8d8d-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

