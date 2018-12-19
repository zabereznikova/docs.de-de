---
title: 'Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 3e03e80279db8c36cb975715f390ff6899d593cb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238324"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="b8003-102">Vorgehensweise: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b8003-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="b8003-103">Die explizite [Schnittstellenimplementierung](../../../csharp/language-reference/keywords/interface.md) erlaubt dem Programmierer auch, zwei Schnittstellen zu implementieren, die über die gleichen Membernamen verfügen, sowie jedem Schnittstellenmember eine separate Implementierung zu geben.</span><span class="sxs-lookup"><span data-stu-id="b8003-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="b8003-104">Dieses Beispiel zeigt die Dimensionen eines Felds in jeweils der metrischen und der englischen Einheit.</span><span class="sxs-lookup"><span data-stu-id="b8003-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="b8003-105">Das Feld [class](../../../csharp/language-reference/keywords/class.md) implementiert zwei Schnittstellen, „IEnglishDimensions“ und „IMetricDimensions“, die die unterschiedlichen Messsysteme darstellen.</span><span class="sxs-lookup"><span data-stu-id="b8003-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="b8003-106">Beide Schnittstellen verfügen über identische Elementnamen, sowie unterschiedliche Länge und Breite.</span><span class="sxs-lookup"><span data-stu-id="b8003-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8003-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8003-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b8003-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b8003-108">Robust Programming</span></span>  
 <span data-ttu-id="b8003-109">Wenn Sie die Standardmessungen in englischen Einheiten durchführen möchten, implementieren Sie die Methoden Länge und Breite normal, und implementieren Sie explizit die Methoden Länge und Breite aus der „IMetricDimensions“-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b8003-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 <span data-ttu-id="b8003-110">In diesem Fall können Sie auf die englischen Einheiten von der Klasseninstanz aus zugreifen und auf die metrischen Einheiten von der Schnittstelleninstanz aus.</span><span class="sxs-lookup"><span data-stu-id="b8003-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b8003-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8003-111">See Also</span></span>

- [<span data-ttu-id="b8003-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b8003-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b8003-113">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="b8003-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="b8003-114">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8003-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
- [<span data-ttu-id="b8003-115">Vorgehensweise: Explizites Implementieren von Schnittstellenmembern</span><span class="sxs-lookup"><span data-stu-id="b8003-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
