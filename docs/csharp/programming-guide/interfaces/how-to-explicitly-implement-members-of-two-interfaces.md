---
title: 'Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierleitfaden)'
description: In diesem C#-Beispiel erfahren Sie, wie Sie explizit zwei Schnittstellen implementieren, die über dieselben Membernamen verfügen, und wie Sie für jeden Schnittstellenmember eine separate Implementierung einrichten.
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 18b1f9cfb1690d35c0bca0a3c79c1b80ae5dd44d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205086"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="c0fd5-103">Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="c0fd5-103">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="c0fd5-104">Die explizite [Schnittstellenimplementierung](../../language-reference/keywords/interface.md) erlaubt dem Programmierer auch, zwei Schnittstellen zu implementieren, die über die gleichen Membernamen verfügen, sowie jedem Schnittstellenmember eine separate Implementierung zu geben.</span><span class="sxs-lookup"><span data-stu-id="c0fd5-104">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="c0fd5-105">Dieses Beispiel zeigt die Dimensionen eines Felds in jeweils der metrischen und der englischen Einheit.</span><span class="sxs-lookup"><span data-stu-id="c0fd5-105">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="c0fd5-106">Das Feld [class](../../language-reference/keywords/class.md) implementiert zwei Schnittstellen, „IEnglishDimensions“ und „IMetricDimensions“, die die unterschiedlichen Messsysteme darstellen.</span><span class="sxs-lookup"><span data-stu-id="c0fd5-106">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="c0fd5-107">Beide Schnittstellen verfügen über identische Elementnamen, sowie unterschiedliche Länge und Breite.</span><span class="sxs-lookup"><span data-stu-id="c0fd5-107">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0fd5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0fd5-108">Example</span></span>  

 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c0fd5-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c0fd5-109">Robust Programming</span></span>  

 <span data-ttu-id="c0fd5-110">Wenn Sie die Standardmessungen in englischen Einheiten durchführen möchten, implementieren Sie die Methoden Länge und Breite normal, und implementieren Sie explizit die Methoden Länge und Breite aus der „IMetricDimensions“-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c0fd5-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="c0fd5-111">In diesem Fall können Sie auf die englischen Einheiten von der Klasseninstanz aus zugreifen und auf die metrischen Einheiten von der Schnittstelleninstanz aus.</span><span class="sxs-lookup"><span data-stu-id="c0fd5-111">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="c0fd5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0fd5-112">See also</span></span>

- [<span data-ttu-id="c0fd5-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c0fd5-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c0fd5-114">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="c0fd5-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="c0fd5-115">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c0fd5-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="c0fd5-116">Explizites Implementieren von Schnittstellenmembern</span><span class="sxs-lookup"><span data-stu-id="c0fd5-116">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
