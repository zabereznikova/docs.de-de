---
title: 'Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierleitfaden)'
description: In diesem C#-Beispiel erfahren Sie, wie Sie Schnittstellenmember explizit implementieren. Der Zugriff auf die Member erfolgt über eine Schnittstelleninstanz.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: a9c019cdcf6e229199d980a2d1913df7c72a2169
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157394"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="cd962-104">Vorgehensweise: Explizites Implementieren von Schnittstellenmembern (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="cd962-104">How to explicitly implement interface members (C# Programming Guide)</span></span>

<span data-ttu-id="cd962-105">Dieses Beispiel deklariert eine [Schnittstelle](../../language-reference/keywords/interface.md), `IDimensions`, und eine Klasse, `Box`, die explizit die Schnittstellenmember `GetLength` und `GetWidth` implementiert.</span><span class="sxs-lookup"><span data-stu-id="cd962-105">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="cd962-106">Die Member werden über eine Schnittstelleninstanz, `dimensions`, erreicht.</span><span class="sxs-lookup"><span data-stu-id="cd962-106">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd962-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd962-107">Example</span></span>  

 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cd962-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="cd962-108">Robust Programming</span></span>  
  
- <span data-ttu-id="cd962-109">Beachten Sie, dass die folgenden Zeilen in der `Main`-Methode auskommentiert werden, da sie Kompilierungsfehler verursachen würden.</span><span class="sxs-lookup"><span data-stu-id="cd962-109">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="cd962-110">Auf ein Schnittstellenmember, das explizit implementiert wird, kann nicht von einer [class](../../language-reference/keywords/class.md)-Instanz zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cd962-110">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="cd962-111">Beachten Sie auch, dass die folgenden Zeilen in der `Main`-Methode erfolgreich die Dimensionen des Felds ausdrucken, da die Methoden von einer Instanz der Schnittstelle aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="cd962-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="cd962-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd962-112">See also</span></span>

- [<span data-ttu-id="cd962-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cd962-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cd962-114">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="cd962-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="cd962-115">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd962-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="cd962-116">Explizites Implementieren von Membern zweier Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd962-116">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
