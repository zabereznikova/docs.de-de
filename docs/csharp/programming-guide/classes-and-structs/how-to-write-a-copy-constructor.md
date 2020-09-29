---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie einen Kopierkonstruktor in C# erstellen, der eine Instanz einer Klasse akzeptiert und eine neue Instanz mit den Werten der Eingabe zurückgibt.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 52fd5aedea6a0e3b7c22e20db523329a00bba9ad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204007"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="8f505-103">Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8f505-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="8f505-104">C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.</span><span class="sxs-lookup"><span data-stu-id="8f505-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f505-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f505-105">Example</span></span>  

 <span data-ttu-id="8f505-106">Im folgenden Beispiel wird von der `Person`-[Klasse](../../language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="8f505-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="8f505-107">Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8f505-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="8f505-108">Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8f505-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="8f505-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f505-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="8f505-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8f505-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8f505-111">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="8f505-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="8f505-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="8f505-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="8f505-113">Finalizer</span><span class="sxs-lookup"><span data-stu-id="8f505-113">Finalizers</span></span>](./destructors.md)
