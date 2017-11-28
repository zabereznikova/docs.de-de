---
title: Checked und Unchecked (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b7b18b39dbfa7ed0818d9ea6e9e62ef79a9f5b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="65acf-102">Checked und Unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="65acf-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="65acf-103">C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="65acf-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="65acf-104">In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="65acf-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="65acf-105">In einem nicht geprüften Kontext wird der arithmetische Überlauf ignoriert, und das Ergebnis wird abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="65acf-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated.</span></span>  
  
-   <span data-ttu-id="65acf-106">[checked](../../../csharp/language-reference/keywords/checked.md) Gibt einen geprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="65acf-106">[checked](../../../csharp/language-reference/keywords/checked.md) Specify checked context.</span></span>  
  
-   <span data-ttu-id="65acf-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Gibt einen ungeprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="65acf-107">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="65acf-108">Wenn weder `checked` noch `unchecked` angegeben wird, ist der Standardkontext von externen Faktoren wie Compileroptionen abhängig.</span><span class="sxs-lookup"><span data-stu-id="65acf-108">If neither `checked` nor `unchecked` is specified, the default context depends on external factors such as compiler options.</span></span>  
  
 <span data-ttu-id="65acf-109">Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:</span><span class="sxs-lookup"><span data-stu-id="65acf-109">The following operations are affected by the overflow checking:</span></span>  
  
-   <span data-ttu-id="65acf-110">Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="65acf-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="65acf-111">`++``--` - (unär)   `+` -   `*``/`</span><span class="sxs-lookup"><span data-stu-id="65acf-111">`++` `--` - (unary)   `+` -   `*` `/`</span></span>  
  
-   <span data-ttu-id="65acf-112">Explizite numerische Konvertierungen zwischen ganzzahligen Typen.</span><span class="sxs-lookup"><span data-stu-id="65acf-112">Explicit numeric conversions between integral types.</span></span>  
  
 <span data-ttu-id="65acf-113">Mit der Compileroption [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) können Sie einen geprüften oder nicht geprüften Kontext für alle ganzzahligen arithmetischen Anweisungen angeben, die nicht explizit im Umfang eines `checked`- oder `unchecked`-Schlüsselworts enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="65acf-113">The [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) compiler option lets you specify checked or unchecked context for all integer arithmetic statements that are not explicitly in the scope of a `checked` or `unchecked` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65acf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65acf-114">See Also</span></span>  
 [<span data-ttu-id="65acf-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="65acf-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="65acf-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="65acf-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="65acf-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="65acf-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="65acf-118">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="65acf-118">Statement Keywords</span></span>](../../../csharp/language-reference/keywords/statement-keywords.md)
