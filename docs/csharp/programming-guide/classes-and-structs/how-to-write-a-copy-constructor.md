---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
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
ms.openlocfilehash: 712d9d5e792d025dd7c91d4c1809eeba96759757
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="293ed-102">Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="293ed-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="293ed-103">C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.</span><span class="sxs-lookup"><span data-stu-id="293ed-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="293ed-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="293ed-104">Example</span></span>  
 <span data-ttu-id="293ed-105">Im folgenden Beispiel wird von der `Person`-[Klasse](../../../csharp/language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="293ed-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="293ed-106">Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="293ed-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="293ed-107">Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="293ed-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 <span data-ttu-id="293ed-108">[!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="293ed-108">[!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293ed-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="293ed-109">See Also</span></span>  
 <span data-ttu-id="293ed-110"><xref:System.ICloneable></span><span class="sxs-lookup"><span data-stu-id="293ed-110"><xref:System.ICloneable></span></span>   
 <span data-ttu-id="293ed-111">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="293ed-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="293ed-112">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="293ed-112">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="293ed-113">[Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="293ed-113">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="293ed-114">Finalizer</span><span class="sxs-lookup"><span data-stu-id="293ed-114">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

