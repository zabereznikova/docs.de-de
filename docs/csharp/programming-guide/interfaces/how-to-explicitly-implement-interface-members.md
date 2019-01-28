---
title: 'Vorgehensweise: Explizites Implementieren von Schnittstellenmembern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 064061b44cca3adb5dde89ecc71fb1f8ea3abf8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562903"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="03f30-102">Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="03f30-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="03f30-103">Dieses Beispiel deklariert eine [Schnittstelle](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `getLength` und `getWidth` implementiert.</span><span class="sxs-lookup"><span data-stu-id="03f30-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="03f30-104">Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.</span><span class="sxs-lookup"><span data-stu-id="03f30-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03f30-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03f30-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="03f30-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="03f30-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="03f30-107">Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden.</span><span class="sxs-lookup"><span data-stu-id="03f30-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="03f30-108">Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../../csharp/language-reference/keywords/class.md)-Instanz zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="03f30-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   <span data-ttu-id="03f30-109">Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="03f30-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="03f30-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03f30-110">See also</span></span>

- [<span data-ttu-id="03f30-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="03f30-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="03f30-112">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="03f30-112">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="03f30-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="03f30-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
- [<span data-ttu-id="03f30-114">Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="03f30-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
