---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie einen Kopierkonstruktor in C# erstellen, der eine Instanz einer Klasse akzeptiert und eine neue Instanz mit den Werten der Eingabe zurückgibt.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 85899d2de05312be921199387cc1155fa8e9d2f1
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098982"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="0f735-103">Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0f735-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="0f735-104">C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f735-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f735-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f735-105">Example</span></span>  

 <span data-ttu-id="0f735-106">Im folgenden Beispiel wird von der `Person`-[Klasse](../../language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="0f735-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="0f735-107">Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0f735-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="0f735-108">Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0f735-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="0f735-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f735-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="0f735-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0f735-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0f735-111">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="0f735-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="0f735-112">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="0f735-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="0f735-113">Finalizer</span><span class="sxs-lookup"><span data-stu-id="0f735-113">Finalizers</span></span>](./destructors.md)
