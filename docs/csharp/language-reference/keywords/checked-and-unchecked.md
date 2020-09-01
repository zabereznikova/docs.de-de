---
description: Checked und Unchecked – C#-Referenz
title: Checked und Unchecked – C#-Referenz
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: a8d6a26e28062da682689bf64a9e38ea5fd158b2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138266"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="968af-103">Checked und Unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="968af-103">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="968af-104">C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="968af-104">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="968af-105">In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="968af-105">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="968af-106">In einem nicht aktivierten Kontext wird der arithmetische Überlauf ignoriert und das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.</span><span class="sxs-lookup"><span data-stu-id="968af-106">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="968af-107">[checked](checked.md) Gibt einen geprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="968af-107">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="968af-108">[unchecked](unchecked.md) Gibt einen ungeprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="968af-108">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="968af-109">Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:</span><span class="sxs-lookup"><span data-stu-id="968af-109">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="968af-110">Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="968af-110">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="968af-111">`++`, `--`, unäres `-`, `+`, `-`, `*`, `/`</span><span class="sxs-lookup"><span data-stu-id="968af-111">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="968af-112">Explizite numerische Konvertierungen zwischen ganzzahligen Typen oder von `float` oder `double` in einen integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="968af-112">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="968af-113">Wenn weder `checked` noch `unchecked` festgelegt ist, wird der Standardkontext für nicht konstante Ausdrücke (Ausdrücke, die zur Laufzeit ausgewertet werden) vom Wert der Compileroption [-checked](../compiler-options/checked-compiler-option.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="968af-113">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="968af-114">Standardmäßig ist der Wert dieser Option nicht festgelegt, und arithmetische Operationen werden in einem nicht geprüften Kontext ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="968af-114">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>

 <span data-ttu-id="968af-115">Für konstante Ausdrücke (Ausdrücke, die zur Kompilierzeit vollständig ausgewertet werden können) ist der Standardkontext immer geprüft.</span><span class="sxs-lookup"><span data-stu-id="968af-115">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="968af-116">Überläufe, die während der Auswertung des Ausdrucks zur Kompilierzeit auftreten, führen zu Kompilierzeitfehlern, wenn der konstante Ausdruck nicht explizit in einen ungeprüften Kontext gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="968af-116">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="968af-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="968af-117">See also</span></span>

- [<span data-ttu-id="968af-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="968af-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="968af-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="968af-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="968af-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="968af-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="968af-121">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="968af-121">Statement Keywords</span></span>](statement-keywords.md)
