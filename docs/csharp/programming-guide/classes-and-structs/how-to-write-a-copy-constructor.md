---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors – C#-Programmierhandbuch'
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714842"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="4f012-102">Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4f012-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="4f012-103">C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.</span><span class="sxs-lookup"><span data-stu-id="4f012-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f012-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f012-104">Example</span></span>  
 <span data-ttu-id="4f012-105">Im folgenden Beispiel wird von der `Person`-[Klasse](../../language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="4f012-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="4f012-106">Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4f012-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="4f012-107">Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4f012-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="4f012-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f012-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="4f012-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4f012-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4f012-110">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="4f012-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="4f012-111">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="4f012-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="4f012-112">Finalizer</span><span class="sxs-lookup"><span data-stu-id="4f012-112">Finalizers</span></span>](./destructors.md)
