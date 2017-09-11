---
title: 'Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: 21
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
ms.openlocfilehash: 808a74f75e4dcbcec47735d98063138e2c7456e5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="9f551-102">Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9f551-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="9f551-103">In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="9f551-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="9f551-104">In diesem Beispiel wird das Schlüsselwort [unsafe](../../../csharp/language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9f551-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="9f551-105">Die Anweisung [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9f551-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="9f551-106">Dadurch wird der Speicherort des Quell- und Zielarrays im Speicher *angeheftet*, damit diese bei der automatischen Speicherbereinigung nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="9f551-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="9f551-107">Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="9f551-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="9f551-108">Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption **/unsafe** kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="9f551-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="9f551-109">Klicken Sie mit der rechten Maustaste auf den Projektnamen, und klicken Sie anschließend auf **Eigenschaften**, um die Option in Visual Studio festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9f551-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="9f551-110">Wählen Sie auf der Registerkarte **Build** die Option **Unsicheren Code zulassen**.</span><span class="sxs-lookup"><span data-stu-id="9f551-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f551-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f551-111">Example</span></span>  
 <span data-ttu-id="9f551-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f551-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]</span></span>  
  
 <span data-ttu-id="9f551-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f551-113">[!code-cs[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f551-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f551-114">See Also</span></span>  
 <span data-ttu-id="9f551-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f551-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9f551-116">[Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f551-116">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="9f551-117">[-unsafe (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="9f551-117">[/unsafe (C# Compiler Options)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) </span></span>  
 [<span data-ttu-id="9f551-118">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9f551-118">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

