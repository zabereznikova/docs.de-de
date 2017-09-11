---
title: 'Gewusst wie: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 16
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
ms.openlocfilehash: 88b96c15f724ee5961c72917308138a045988225
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="c3f5b-102">Gewusst wie: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c3f5b-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="c3f5b-103">Dieses Beispiel deklariert eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `getLength` und `getWidth` implementiert.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="c3f5b-104">Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3f5b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3f5b-105">Example</span></span>  
 <span data-ttu-id="c3f5b-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c3f5b-106">[!code-cs[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c3f5b-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c3f5b-107">Robust Programming</span></span>  
  
-   <span data-ttu-id="c3f5b-108">Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-108">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="c3f5b-109">Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../../csharp/language-reference/keywords/class.md)-Instanz zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c3f5b-109">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     <span data-ttu-id="c3f5b-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c3f5b-110">[!code-cs[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]</span></span>  
  
-   <span data-ttu-id="c3f5b-111">Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="c3f5b-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     <span data-ttu-id="c3f5b-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c3f5b-112">[!code-cs[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f5b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3f5b-113">See Also</span></span>  
 <span data-ttu-id="c3f5b-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3f5b-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c3f5b-115">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3f5b-115">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="c3f5b-116">[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3f5b-116">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="c3f5b-117">Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c3f5b-117">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)

