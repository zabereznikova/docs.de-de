---
title: 'Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="b90f2-102">Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b90f2-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="b90f2-103">In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="b90f2-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="b90f2-104">In diesem Beispiel wird das Schlüsselwort [unsafe](../../../csharp/language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b90f2-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="b90f2-105">Die Anweisung [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b90f2-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="b90f2-106">Dadurch wird der Speicherort des Quell- und Zielarrays im Speicher *angeheftet*, damit diese bei der automatischen Speicherbereinigung nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b90f2-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="b90f2-107">Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b90f2-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="b90f2-108">Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption **/unsafe** kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b90f2-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="b90f2-109">Klicken Sie mit der rechten Maustaste auf den Projektnamen, und klicken Sie anschließend auf **Eigenschaften**, um die Option in Visual Studio festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b90f2-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="b90f2-110">Wählen Sie auf der Registerkarte **Build** die Option **Unsicheren Code zulassen**.</span><span class="sxs-lookup"><span data-stu-id="b90f2-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b90f2-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b90f2-111">Example</span></span>  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b90f2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b90f2-112">See Also</span></span>  
 [<span data-ttu-id="b90f2-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b90f2-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b90f2-114">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="b90f2-114">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="b90f2-115">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="b90f2-115">/unsafe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [<span data-ttu-id="b90f2-116">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b90f2-116">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
