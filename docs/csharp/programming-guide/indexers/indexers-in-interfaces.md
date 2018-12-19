---
title: Indexer in Schnittstellen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: ff636691ea2f4dacd13fbd2a336f0023ed65750b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235659"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="ebe48-102">Indexer in Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ebe48-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ebe48-103">Indexer können für eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md) deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ebe48-103">Indexers can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="ebe48-104">Accessoren für Schnittstellenindexer unterscheiden sich von den Accessoren für [Klassen](../../../csharp/language-reference/keywords/class.md)-Indexer in den folgenden Punkten:</span><span class="sxs-lookup"><span data-stu-id="ebe48-104">Accessors of interface indexers differ from the accessors of [class](../../../csharp/language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
-   <span data-ttu-id="ebe48-105">Schnittstellenaccessoren verwenden keine Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="ebe48-105">Interface accessors do not use modifiers.</span></span>  
  
-   <span data-ttu-id="ebe48-106">Ein Schnittstellenaccessor enthält keinen Text.</span><span class="sxs-lookup"><span data-stu-id="ebe48-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="ebe48-107">Der Zweck eines Accessors besteht darin anzugeben, ob der Indexer gleichzeitig Lese- und Schreibzugriff, nur Lesezugriff oder nur Schreibzugriff besitzt.</span><span class="sxs-lookup"><span data-stu-id="ebe48-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="ebe48-108">Das folgende Beispiel zeigt den Accessor für einen Schnittstellenindexer:</span><span class="sxs-lookup"><span data-stu-id="ebe48-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 <span data-ttu-id="ebe48-109">Die Signatur eines Indexers muss sich von den Signaturen aller anderen in derselben Schnittstelle deklarierten Indexer unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ebe48-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebe48-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebe48-110">Example</span></span>  
 <span data-ttu-id="ebe48-111">Das folgende Beispiel zeigt, wie Schnittstellenindexer implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebe48-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 <span data-ttu-id="ebe48-112">Im vorherigen Beispiel könnte der Schnittstellenmember durch Verwendung des vollqualifizierten Namens des Schnittstellenmembers explizit implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebe48-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="ebe48-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ebe48-113">For example:</span></span>  
  
```  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="ebe48-114">Der vollqualifizierte Name ist jedoch nur erforderlich, um Mehrdeutigkeiten zu vermeiden, wenn mehr als eine Schnittstelle mit derselben Indexersignatur von der Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ebe48-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="ebe48-115">Wenn z.B. eine `Employee`-Klasse die beiden Schnittstellen `ICitizen` und `IEmployee` implementiert und beide Schnittstellen dieselbe Indexersignatur besitzen, ist die explizite Implementierung des Schnittstellenmembers erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ebe48-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="ebe48-116">Das bedeutet, dass die folgende Indexerdeklaration:</span><span class="sxs-lookup"><span data-stu-id="ebe48-116">That is, the following indexer declaration:</span></span>  
  
```  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="ebe48-117">den Indexer für die Schnittstelle `IEmployee` implementiert. Dahingegen implementiert die folgende Deklaration:</span><span class="sxs-lookup"><span data-stu-id="ebe48-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="ebe48-118">den Indexer für die Schnittstelle `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="ebe48-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe48-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebe48-119">See Also</span></span>

- [<span data-ttu-id="ebe48-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ebe48-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ebe48-121">Indexer</span><span class="sxs-lookup"><span data-stu-id="ebe48-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="ebe48-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ebe48-122">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [<span data-ttu-id="ebe48-123">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebe48-123">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
