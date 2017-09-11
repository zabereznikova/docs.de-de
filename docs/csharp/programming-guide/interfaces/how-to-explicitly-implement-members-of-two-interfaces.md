---
title: 'Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
caps.latest.revision: 15
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
ms.openlocfilehash: 1446233793e3fd61f09d7da99f4f68cb7b3eabb8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="fc8b3-102">Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fc8b3-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="fc8b3-103">Die explizite [Schnittstellenimplementierung](../../../csharp/language-reference/keywords/interface.md) erlaubt dem Programmierer auch, zwei Schnittstellen zu implementieren, die über die gleichen Membernamen verfügen, sowie jedem Schnittstellenmember eine separate Implementierung zu geben.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="fc8b3-104">Dieses Beispiel zeigt die Dimensionen eines Felds in jeweils der metrischen und der englischen Einheit.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="fc8b3-105">Das Feld [class](../../../csharp/language-reference/keywords/class.md) implementiert zwei Schnittstellen, „IEnglishDimensions“ und „IMetricDimensions“, die die unterschiedlichen Messsysteme darstellen.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="fc8b3-106">Beide Schnittstellen verfügen über identische Elementnamen, sowie unterschiedliche Länge und Breite.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc8b3-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc8b3-107">Example</span></span>  
 <span data-ttu-id="fc8b3-108">[!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8b3-108">[!code-cs[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fc8b3-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="fc8b3-109">Robust Programming</span></span>  
 <span data-ttu-id="fc8b3-110">Wenn Sie die Standardmessungen in englischen Einheiten durchführen möchten, implementieren Sie die Methoden Länge und Breite normal, und implementieren Sie explizit die Methoden Länge und Breite aus der „IMetricDimensions“-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 <span data-ttu-id="fc8b3-111">[!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8b3-111">[!code-cs[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="fc8b3-112">In diesem Fall können Sie auf die englischen Einheiten von der Klasseninstanz aus zugreifen und auf die metrischen Einheiten von der Schnittstelleninstanz aus.</span><span class="sxs-lookup"><span data-stu-id="fc8b3-112">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 <span data-ttu-id="fc8b3-113">[!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="fc8b3-113">[!code-cs[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8b3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc8b3-114">See Also</span></span>  
 <span data-ttu-id="fc8b3-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc8b3-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fc8b3-116">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc8b3-116">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="fc8b3-117">[Schnittstellen](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="fc8b3-117">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="fc8b3-118">Gewusst wie: Explizites Implementieren von Schnittstellenmembern</span><span class="sxs-lookup"><span data-stu-id="fc8b3-118">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)

