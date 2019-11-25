---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 4ac7ccb55775019eb86d5345797d2fd74d3b9527
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970393"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="ad0dd-102">Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ad0dd-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="ad0dd-103">C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad0dd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad0dd-104">Example</span></span>  
 <span data-ttu-id="ad0dd-105">Im folgenden Beispiel wird von der `Person`-[Klasse](../../language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="ad0dd-106">Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="ad0dd-107">Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ad0dd-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="ad0dd-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad0dd-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="ad0dd-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ad0dd-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ad0dd-110">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="ad0dd-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="ad0dd-111">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="ad0dd-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="ad0dd-112">Finalizer</span><span class="sxs-lookup"><span data-stu-id="ad0dd-112">Finalizers</span></span>](./destructors.md)
