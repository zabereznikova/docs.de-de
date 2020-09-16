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
ms.openlocfilehash: ea7bc17cba19137b4e4ca2d8cddb32e6630887c9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544842"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="fa735-102">Systeminterner x:Code-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="fa735-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="fa735-103">Ermöglicht die Platzierung von Code in einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="fa735-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="fa735-104">Dieser Code kann entweder von jeder XAML-Prozessor Implementierung kompiliert werden, die XAML kompiliert, oder in der XAML-Produktion verbleiben, um später verwendet zu werden, z. b. die Interpretation durch eine Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="fa735-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="fa735-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="fa735-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="fa735-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa735-106">Remarks</span></span>

<span data-ttu-id="fa735-107">Der Code im `x:Code` XAML-Direktivenelement wird immer noch innerhalb des allgemeinen XML-Namespace und der bereitgestellten XAML-Namespaces interpretiert.</span><span class="sxs-lookup"><span data-stu-id="fa735-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="fa735-108">Daher ist es normalerweise erforderlich, den Code, der für `x:Code` innerhalb eines Segments verwendet wird, einzuschließen `CDATA` .</span><span class="sxs-lookup"><span data-stu-id="fa735-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="fa735-109">`x:Code` ist nicht für alle möglichen Bereitstellungs Mechanismen einer XAML-Produktion zulässig.</span><span class="sxs-lookup"><span data-stu-id="fa735-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="fa735-110">In bestimmten Frameworks (z. b. WPF) muss der Code kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="fa735-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="fa735-111">In anderen Frameworks ist die `x:Code` Verwendung möglicherweise in der Regel nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fa735-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="fa735-112">Für Frameworks, die verwalteten `x:Code` Inhalt zulassen, wird der korrekte sprach Compiler, der für-Inhalte verwendet wird, `x:Code` durch Einstellungen und Ziele des enthaltenden Projekts bestimmt, das zum Kompilieren der Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa735-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="fa735-113">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="fa735-113">WPF Usage Notes</span></span>

<span data-ttu-id="fa735-114">Der in `x:Code` für WPF deklarierte Code hat mehrere wichtige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="fa735-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="fa735-115">Das `x:Code` Direktivenelement muss ein unmittelbares untergeordnetes Element des Stamm Elements der XAML-Produktion sein.</span><span class="sxs-lookup"><span data-stu-id="fa735-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="fa735-116">die [x:Class-Direktive](xclass-directive.md) muss für das übergeordnete root-Element bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fa735-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="fa735-117">Der in platzierte Code `x:Code` wird von der Kompilierung behandelt, um innerhalb des Bereichs der partiellen Klasse zu sein, die bereits für diese XAML-Seite erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fa735-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="fa735-118">Daher müssen alle von Ihnen definierten Codes Member oder Variablen dieser partiellen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="fa735-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="fa735-119">Sie können keine zusätzlichen Klassen definieren, außer indem Sie eine Klasse in der partiellen Klasse Schachteln (die Schachtelung ist zulässig, aber nicht typisch, weil auf geschachtelte Klassen in XAML nicht verwiesen werden kann).</span><span class="sxs-lookup"><span data-stu-id="fa735-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="fa735-120">Andere CLR-Namespaces als der Namespace, der für die vorhandene partielle Klasse verwendet wird, können nicht definiert oder zu hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fa735-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="fa735-121">Verweise auf Code Entitäten außerhalb des CLR-Namespace der partiellen Klasse müssen alle voll qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="fa735-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="fa735-122">Wenn Member, die deklariert werden, über Schreibungen für die partiell baren Member der partiellen Klasse sind, muss dies mit dem sprachspezifischen Überschreibungs Schlüsselwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fa735-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="fa735-123">Wenn im `x:Code` Bereich deklarierte Member mit Membern der partiellen Klasse, die aus dem XAML erstellt wurden, so in Konflikt stehen, dass der Compiler den Konflikt meldet, kann die XAML-Datei nicht kompiliert oder geladen werden.</span><span class="sxs-lookup"><span data-stu-id="fa735-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa735-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa735-124">See also</span></span>

- [<span data-ttu-id="fa735-125">x:Class-Direktive</span><span class="sxs-lookup"><span data-stu-id="fa735-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="fa735-126">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="fa735-126">Code-Behind and XAML in WPF</span></span>](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [<span data-ttu-id="fa735-127">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="fa735-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
