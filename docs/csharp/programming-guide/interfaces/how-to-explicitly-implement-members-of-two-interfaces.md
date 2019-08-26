---
title: 'Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 1d4dd0485be1d859e3e9594ab1558a907b8f1f7a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589195"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="71f30-102">Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="71f30-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="71f30-103">Die explizite [Schnittstellenimplementierung](../../language-reference/keywords/interface.md) erlaubt dem Programmierer auch, zwei Schnittstellen zu implementieren, die über die gleichen Membernamen verfügen, sowie jedem Schnittstellenmember eine separate Implementierung zu geben.</span><span class="sxs-lookup"><span data-stu-id="71f30-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="71f30-104">Dieses Beispiel zeigt die Dimensionen eines Felds in jeweils der metrischen und der englischen Einheit.</span><span class="sxs-lookup"><span data-stu-id="71f30-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="71f30-105">Das Feld [class](../../language-reference/keywords/class.md) implementiert zwei Schnittstellen, „IEnglishDimensions“ und „IMetricDimensions“, die die unterschiedlichen Messsysteme darstellen.</span><span class="sxs-lookup"><span data-stu-id="71f30-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="71f30-106">Beide Schnittstellen verfügen über identische Elementnamen, sowie unterschiedliche Länge und Breite.</span><span class="sxs-lookup"><span data-stu-id="71f30-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71f30-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71f30-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="71f30-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="71f30-108">Robust Programming</span></span>  
 <span data-ttu-id="71f30-109">Wenn Sie die Standardmessungen in englischen Einheiten durchführen möchten, implementieren Sie die Methoden Länge und Breite normal, und implementieren Sie explizit die Methoden Länge und Breite aus der „IMetricDimensions“-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="71f30-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="71f30-110">In diesem Fall können Sie auf die englischen Einheiten von der Klasseninstanz aus zugreifen und auf die metrischen Einheiten von der Schnittstelleninstanz aus.</span><span class="sxs-lookup"><span data-stu-id="71f30-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="71f30-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71f30-111">See also</span></span>

- [<span data-ttu-id="71f30-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="71f30-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="71f30-113">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="71f30-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="71f30-114">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="71f30-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="71f30-115">Vorgehensweise: Explizites Implementieren von Schnittstellenmembern</span><span class="sxs-lookup"><span data-stu-id="71f30-115">How to: Explicitly Implement Interface Members</span></span>](./how-to-explicitly-implement-interface-members.md)
