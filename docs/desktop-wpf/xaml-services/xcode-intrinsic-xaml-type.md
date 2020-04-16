---
title: Systeminterner x:Code-XAML-Typ
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432803"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="2301b-102">Systeminterner x:Code-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="2301b-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="2301b-103">Ermöglicht die Platzierung von Code in einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="2301b-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="2301b-104">Dieser Code kann entweder von jeder XAML-Prozessorimplementierung kompiliert werden, die XAML kompiliert, oder in der XAML-Produktion für spätere Verwendungen, z. B. Interpretation durch eine Laufzeit, belassen werden.</span><span class="sxs-lookup"><span data-stu-id="2301b-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="2301b-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="2301b-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="2301b-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2301b-106">Remarks</span></span>

<span data-ttu-id="2301b-107">Der Code `x:Code` innerhalb des XAML-Direktivierungselements wird weiterhin im allgemeinen XML-Namespace und in den bereitgestellten XAML-Namespaces interpretiert.</span><span class="sxs-lookup"><span data-stu-id="2301b-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="2301b-108">Daher ist es in der Regel notwendig, den Code, der für `x:Code` ein `CDATA` Segment verwendet wird, einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="2301b-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="2301b-109">`x:Code`ist nicht für alle möglichen Bereitstellungsmechanismen einer XAML-Produktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="2301b-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="2301b-110">In bestimmten Frameworks (z. B. WPF) muss der Code kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="2301b-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="2301b-111">In anderen Frameworks ist die `x:Code` Verwendung im Allgemeinen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2301b-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="2301b-112">Bei Frameworks, `x:Code` die verwalteten Inhalt zulassen, `x:Code` wird der richtige Sprachcompiler für Den Inhalt durch Einstellungen und Ziele des enthaltenden Projekts bestimmt, das zum Kompilieren der Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2301b-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="2301b-113">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="2301b-113">WPF Usage Notes</span></span>

<span data-ttu-id="2301b-114">Code, `x:Code` der für WPF deklariert wurde, weist mehrere bemerkenswerte Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="2301b-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="2301b-115">Das `x:Code` Direktivenelement muss ein sofortiges untergeordnetes Element des Stammelements der XAML-Produktion sein.</span><span class="sxs-lookup"><span data-stu-id="2301b-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="2301b-116">[x:Klassendirektive](xclass-directive.md) muss für das übergeordnete Stammelement bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2301b-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="2301b-117">Der darin `x:Code` platzierte Code wird durch Kompilierung behandelt, um innerhalb des Bereichs der partiellen Klasse zu liegen, die bereits für diese XAML-Seite erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2301b-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="2301b-118">Daher muss der gesamte Code, den Sie definieren, Member oder Variablen dieser partiellen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="2301b-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="2301b-119">Sie können keine zusätzlichen Klassen definieren, außer durch Verschachteln einer Klasse innerhalb der partiellen Klasse (Verschachtelung ist zulässig, aber sie ist nicht typisch, da geschachtelte Klassen in XAML nicht referenziert werden können).</span><span class="sxs-lookup"><span data-stu-id="2301b-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="2301b-120">CLR-Namespaces, die nicht der Namespace sind, der für die vorhandene Partipartklasse verwendet wird, können nicht definiert oder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2301b-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="2301b-121">Verweise auf Codeentitäten außerhalb des CLR-Namespace der Teilklasse müssen alle vollständig qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="2301b-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="2301b-122">Wenn Member deklariert werden, die überschrieben werden, müssen die überschreibbaren Member der Partipartklasse mit dem sprachspezifischen Überschreibungsschlüsselwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2301b-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="2301b-123">Wenn Member, `x:Code` die im Gültigkeitsbereich deklariert wurden, mit Membern der partiellen Klasse in Konflikt stehen, die aus dem XAML erstellt wurden, so dass der Compiler den Konflikt meldet, kann die XAML-Datei nicht kompiliert oder geladen werden.</span><span class="sxs-lookup"><span data-stu-id="2301b-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="2301b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2301b-124">See also</span></span>

- [<span data-ttu-id="2301b-125">x:Class-Direktive</span><span class="sxs-lookup"><span data-stu-id="2301b-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="2301b-126">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="2301b-126">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="2301b-127">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="2301b-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
