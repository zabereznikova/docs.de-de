---
title: unsafe (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 367a080cf58514b3ffcc30c17d8fe7bb07e0e9ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="0ea16-102">unsafe (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0ea16-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="0ea16-103">Das Schlüsselwort `unsafe` kennzeichnet einen unsicheren Kontext, der für alle Zeigeroperationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0ea16-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="0ea16-104">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ea16-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="0ea16-105">Sie können bei der Deklaration eines Typs oder Members den Modifizierer `unsafe` verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ea16-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="0ea16-106">Daraufhin wird der gesamte Text des Typs oder Members als unsicherer Kontext angesehen.</span><span class="sxs-lookup"><span data-stu-id="0ea16-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="0ea16-107">Hier sehen Sie eine Methode, die mit dem Modifizierer `unsafe` deklariert wurde:</span><span class="sxs-lookup"><span data-stu-id="0ea16-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="0ea16-108">Der unsichere Kontext erstreckt sich von der Parameterliste bis zum Ende der Methode, weshalb in der Parameterliste auch Zeiger verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="0ea16-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="0ea16-109">Sie können auch einen unsafe-Block verwenden, um die Verwendung von unsicherem Code in diesem Block zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0ea16-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="0ea16-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0ea16-110">For example:</span></span>  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="0ea16-111">Um unsicheren Code kompilieren zu können, müssen Sie die Compileroption [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="0ea16-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="0ea16-112">Unsicherer Code kann nicht von der Common Language Runtime überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0ea16-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ea16-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ea16-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0ea16-114">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="0ea16-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ea16-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ea16-115">See Also</span></span>  
 [<span data-ttu-id="0ea16-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0ea16-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0ea16-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0ea16-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0ea16-118">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="0ea16-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0ea16-119">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0ea16-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="0ea16-120">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="0ea16-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="0ea16-121">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="0ea16-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
