---
title: "Gewusst wie: Verwenden der Operatorüberladung zum Erstellen einer Klasse für komplexe Zahlen (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- complex numbers [C#]
- classes [C#], operator overloading
- operator overloading [C#], complex numbers
- operator overloading [C#], using to create classes
- operators [C#], overloading to create a complex number class
ms.assetid: c9b8d982-5112-413f-bae3-b42ae3248ddf
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
ms.openlocfilehash: 2ce629320744d46787aaabba48740f05c917fdcb
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-operator-overloading-to-create-a-complex-number-class-c-programming-guide"></a><span data-ttu-id="7c3b7-102">Gewusst wie: Verwenden der Operatorüberladung zum Erstellen einer Klasse für komplexe Zahlen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7c3b7-102">How to: Use Operator Overloading to Create a Complex Number Class (C# Programming Guide)</span></span>
<span data-ttu-id="7c3b7-103">In diesem Beispiel wird gezeigt, wie Sie die Operatorüberladung verwenden können, um die komplexe Zahlenklasse `Complex` zu erstellen, die die komplexe Addition definiert.</span><span class="sxs-lookup"><span data-stu-id="7c3b7-103">This example shows how you can use operator overloading to create a complex number class `Complex` that defines complex addition.</span></span> <span data-ttu-id="7c3b7-104">Das Programm zeigt den Imaginär- und den Realteil der Zahlen und das Ergebnis der Addition durch Überschreiben der `ToString`-Methode an.</span><span class="sxs-lookup"><span data-stu-id="7c3b7-104">The program displays the imaginary and the real parts of the numbers and the addition result using an override of the `ToString` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c3b7-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c3b7-105">Example</span></span>  
 <span data-ttu-id="7c3b7-106">[!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7c3b7-106">[!code-cs[csProgGuideStatements#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-use-operator-overloading-to-create-a-complex-number-class_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c3b7-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c3b7-107">See Also</span></span>  
 <span data-ttu-id="7c3b7-108">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7c3b7-108">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7c3b7-109">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="7c3b7-109">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="7c3b7-110">[Operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="7c3b7-110">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 [<span data-ttu-id="7c3b7-111">Why are overloaded operators always static in C#? (Warum sind überladene Operatoren in C# immer statisch?)</span><span class="sxs-lookup"><span data-stu-id="7c3b7-111">Why are overloaded operators always static in C#?</span></span>](http://go.microsoft.com/fwlink/?LinkId=112383)

