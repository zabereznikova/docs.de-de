---
title: 'Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: dff094aca237ed6146bd9b52813c40549bc99b9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627784"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="9467a-102">Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="9467a-102">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="9467a-103">Dieses Beispiel deklariert eine [Schnittstelle](../../language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `GetLength` und `GetWidth` implementiert.</span><span class="sxs-lookup"><span data-stu-id="9467a-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="9467a-104">Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.</span><span class="sxs-lookup"><span data-stu-id="9467a-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9467a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9467a-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="9467a-106">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="9467a-106">Robust Programming</span></span>  
  
- <span data-ttu-id="9467a-107">Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden.</span><span class="sxs-lookup"><span data-stu-id="9467a-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="9467a-108">Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../language-reference/keywords/class.md)-Instanz zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="9467a-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="9467a-109">Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="9467a-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="9467a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9467a-110">See also</span></span>

- [<span data-ttu-id="9467a-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9467a-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9467a-112">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="9467a-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="9467a-113">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9467a-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="9467a-114">Explizites Implementieren von Membern zweier Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9467a-114">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
