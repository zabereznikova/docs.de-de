---
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
ms.openlocfilehash: 8ee4c481a30dce30029fbe8cc26f4798b523a7ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173639"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="ea9a5-102">Checked und Unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ea9a5-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="ea9a5-103">C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="ea9a5-104">In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="ea9a5-105">In einem nicht aktivierten Kontext wird der arithmetische Überlauf ignoriert und das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="ea9a5-106">[checked](checked.md) Gibt einen geprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-106">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="ea9a5-107">[unchecked](unchecked.md) Gibt einen ungeprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-107">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="ea9a5-108">Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:</span><span class="sxs-lookup"><span data-stu-id="ea9a5-108">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="ea9a5-109">Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="ea9a5-109">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="ea9a5-110">`++`, `--`, unäres `-`, `+`, `-`, `*`, `/`</span><span class="sxs-lookup"><span data-stu-id="ea9a5-110">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="ea9a5-111">Explizite numerische Konvertierungen zwischen ganzzahligen Typen oder von `float` oder `double` in einen integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-111">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="ea9a5-112">Wenn weder `checked` noch `unchecked` festgelegt ist, wird der Standardkontext für nicht konstante Ausdrücke (Ausdrücke, die zur Laufzeit ausgewertet werden) vom Wert der Compileroption [-checked](../compiler-options/checked-compiler-option.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-112">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="ea9a5-113">Standardmäßig ist der Wert dieser Option nicht festgelegt, und arithmetische Operationen werden in einem nicht geprüften Kontext ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-113">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>

 <span data-ttu-id="ea9a5-114">Für konstante Ausdrücke (Ausdrücke, die zur Kompilierzeit vollständig ausgewertet werden können) ist der Standardkontext immer geprüft.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-114">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="ea9a5-115">Überläufe, die während der Auswertung des Ausdrucks zur Kompilierzeit auftreten, führen zu Kompilierzeitfehlern, wenn der konstante Ausdruck nicht explizit in einen ungeprüften Kontext gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="ea9a5-115">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea9a5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea9a5-116">See also</span></span>

- [<span data-ttu-id="ea9a5-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ea9a5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ea9a5-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ea9a5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ea9a5-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ea9a5-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ea9a5-120">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ea9a5-120">Statement Keywords</span></span>](statement-keywords.md)
