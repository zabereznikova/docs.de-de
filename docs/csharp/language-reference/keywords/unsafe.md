---
title: unsafe (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
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
ms.openlocfilehash: ceba9e518caf6618cf2f457b930ce08f18273d8c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-c-reference"></a><span data-ttu-id="953ee-102">unsafe (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="953ee-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="953ee-103">Das Schlüsselwort `unsafe` kennzeichnet einen unsicheren Kontext, der für alle Zeigeroperationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="953ee-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="953ee-104">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="953ee-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="953ee-105">Sie können bei der Deklaration eines Typs oder Members den Modifizierer `unsafe` verwenden.</span><span class="sxs-lookup"><span data-stu-id="953ee-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="953ee-106">Daraufhin wird der gesamte Text des Typs oder Members als unsicherer Kontext angesehen.</span><span class="sxs-lookup"><span data-stu-id="953ee-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="953ee-107">Hier sehen Sie eine Methode, die mit dem Modifizierer `unsafe` deklariert wurde:</span><span class="sxs-lookup"><span data-stu-id="953ee-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="953ee-108">Der unsichere Kontext erstreckt sich von der Parameterliste bis zum Ende der Methode, weshalb in der Parameterliste auch Zeiger verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="953ee-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="953ee-109">Sie können auch einen unsafe-Block verwenden, um die Verwendung von unsicherem Code in diesem Block zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="953ee-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="953ee-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="953ee-110">For example:</span></span>  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="953ee-111">Um unsicheren Code kompilieren zu können, müssen Sie die Compileroption [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="953ee-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="953ee-112">Unsicherer Code kann nicht von der Common Language Runtime überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="953ee-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="953ee-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="953ee-113">Example</span></span>  
 <span data-ttu-id="953ee-114">[!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="953ee-114">[!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="953ee-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="953ee-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="953ee-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="953ee-116">See Also</span></span>  
 <span data-ttu-id="953ee-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="953ee-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="953ee-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="953ee-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="953ee-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="953ee-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="953ee-120">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="953ee-120">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 <span data-ttu-id="953ee-121">[Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="953ee-121">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="953ee-122">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="953ee-122">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

