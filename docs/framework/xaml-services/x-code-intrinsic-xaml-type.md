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
ms.openlocfilehash: 8d0dbc03bb5eaedd89d5a6ce97d625a51507e820
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58050596"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="8ded9-102">Systeminterner x:Code-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="8ded9-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="8ded9-103">Ermöglicht die Platzierung von Code innerhalb einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="8ded9-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="8ded9-104">Dieser Code kann entweder von einer Implementierung der XAML-Prozessor kompiliert werden, die XAML, oder von links in der XAML-Produktion zur späteren Verwendung für z.B. Interpretation von einer Runtime kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="8ded9-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="8ded9-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="8ded9-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ded9-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ded9-106">Remarks</span></span>  
 <span data-ttu-id="8ded9-107">Der Code innerhalb der `x:Code` XAML-Anweisungselement ist immer noch innerhalb der allgemeinen XML-Namespace interpretiert und die XAML-Namespaces zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="8ded9-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="8ded9-108">Daher ist es normalerweise notwendig, schließen Sie den Code zum `x:Code` innerhalb einer `CDATA` Segment.</span><span class="sxs-lookup"><span data-stu-id="8ded9-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="8ded9-109">`x:Code` ist für alle möglichen Bereitstellungsmechanismen einer XAML-Produktion nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8ded9-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="8ded9-110">In bestimmten Frameworks (z. B. WPF) muss der Code kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8ded9-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="8ded9-111">In anderen Frameworks `x:Code` Nutzung kann im Allgemeinen als unzulässig erklärt werden.</span><span class="sxs-lookup"><span data-stu-id="8ded9-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="8ded9-112">Für Frameworks, mit denen verwaltete `x:Code` Inhalt, für die Verwendung der richtigen Sprachcompiler `x:Code` Inhalt richtet sich nach den Einstellungen und Ziele des enthaltenden Projekts, das verwendet wird, um die Anwendung zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8ded9-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="8ded9-113">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="8ded9-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="8ded9-114">Code deklariert in `x:Code` für WPF mehrere wichtige Einschränkungen aufweist:</span><span class="sxs-lookup"><span data-stu-id="8ded9-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="8ded9-115">Die `x:Code` -Anweisungselement muss ein unmittelbar untergeordnetes Element des Stammelements der XAML-Produktion sein.</span><span class="sxs-lookup"><span data-stu-id="8ded9-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="8ded9-116">[X: Class-Anweisung](x-class-directive.md) muss für das Stammelement der übergeordneten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8ded9-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="8ded9-117">Der Code eingefügt, in `x:Code` behandelt werden, von der Kompilierung innerhalb des Bereichs der partiellen Klasse sein, die bereits für diese XAML-Seite erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8ded9-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="8ded9-118">Aus diesem Grund muss alle Code, den Sie definieren, Member oder Variablen der partiellen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="8ded9-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="8ded9-119">Sie können keine zusätzliche Klassen definieren, als durch das Schachteln einer Klasse in der partiellen Klasse (Schachtelung ist zulässig, aber es ist nicht typisch, da geschachtelte Klassen in XAML verwiesen werden können).</span><span class="sxs-lookup"><span data-stu-id="8ded9-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="8ded9-120">CLR-Namespaces als dem, der für die vorhandene partielle Klasse verwendet wird, kann nicht definiert oder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8ded9-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="8ded9-121">Verweise auf Entitäten außerhalb der partiellen Klasse CLR-Namespace müssen alle vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="8ded9-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="8ded9-122">Wenn Mitglieder, die deklariert wird, überschreibungen, um die partielle Klasse überschreibbare Member sind, muss dies mit dem sprachspezifischen Override-Schlüsselwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8ded9-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="8ded9-123">Wenn Sie im Member deklariert `x:Code` Bereich in Konflikt mit Membern der partiellen Klasse aus dem XAML erstellt, so, dass der Compiler den Konflikt, meldet die XAML-Datei kann nicht kompiliert oder geladen.</span><span class="sxs-lookup"><span data-stu-id="8ded9-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ded9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ded9-124">See also</span></span>
- [<span data-ttu-id="8ded9-125">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8ded9-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="8ded9-126">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="8ded9-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="8ded9-127">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="8ded9-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
