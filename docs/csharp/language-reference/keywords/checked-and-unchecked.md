---
title: Checked und Unchecked (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 26ea8a7864d93b8d64661db2b0dc1df6634f989a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="f23ac-102">Checked und Unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f23ac-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="f23ac-103">C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f23ac-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="f23ac-104">In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="f23ac-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="f23ac-105">In einem nicht geprüften Kontext wird der arithmetische Überlauf ignoriert, und das Ergebnis wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="f23ac-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="f23ac-106">[checked](../../../csharp/language-reference/keywords/checked.md) Gibt einen geprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="f23ac-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="f23ac-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Gibt einen ungeprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="f23ac-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="f23ac-108">Wenn weder `checked` noch `unchecked` angegeben wird, ist der Standardkontext von externen Faktoren wie Compileroptionen abhängig.</span><span class="sxs-lookup"><span data-stu-id="f23ac-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="f23ac-109">Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:</span><span class="sxs-lookup"><span data-stu-id="f23ac-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="f23ac-110">Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="f23ac-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="f23ac-111">`++``--` - (unär)   `+` -   `*``/`</span><span class="sxs-lookup"><span data-stu-id="f23ac-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="f23ac-112">Explizite numerische Konvertierungen zwischen ganzzahligen Typen.</span><span class="sxs-lookup"><span data-stu-id="f23ac-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="f23ac-113">Mit der Compileroption [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) können Sie einen geprüften oder nicht geprüften Kontext für alle ganzzahligen arithmetischen Anweisungen angeben, die nicht explizit im Umfang eines `checked`- oder `unchecked`-Schlüsselworts enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f23ac-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23ac-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f23ac-114">See Also</span></span>  
 [<span data-ttu-id="f23ac-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f23ac-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f23ac-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f23ac-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f23ac-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f23ac-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f23ac-118">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f23ac-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
