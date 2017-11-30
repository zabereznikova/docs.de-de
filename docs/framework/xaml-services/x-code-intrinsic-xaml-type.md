---
title: Systeminterner x:Code-XAML-Typ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d1b21e2a654b18547c8da7da724c87946724f71f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="ceee3-102">Systeminterner x:Code-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="ceee3-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="ceee3-103">Ermöglicht die Platzierung von Code in einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="ceee3-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="ceee3-104">Solcher Code kann entweder durch die Implementierung einer XAML-Prozessor kompiliert werden, die XAML oder links in der die Verwendung von XAML-Produktion höher verwendet, z. B. Interpretation von einer Laufzeit kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ceee3-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="ceee3-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="ceee3-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="ceee3-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ceee3-106">Remarks</span></span>  
 <span data-ttu-id="ceee3-107">Der Code innerhalb der `x:Code` -XAML-Direktivenelement ist immer noch innerhalb der allgemeinen XML-Namespace interpretiert und die Verwendung von XAML-Namespaces bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ceee3-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="ceee3-108">Daher ist es normalerweise erforderlich, schließen Sie den Code zum `x:Code` innerhalb einer `CDATA` Segment.</span><span class="sxs-lookup"><span data-stu-id="ceee3-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="ceee3-109">`x:Code`ist für alle möglichen Bereitstellungsmechanismen einer XAML-Produktion nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ceee3-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="ceee3-110">In bestimmten Frameworks (z. B. WPF) muss der Code kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ceee3-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="ceee3-111">In anderen Frameworks `x:Code` Nutzung kann im Allgemeinen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ceee3-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="ceee3-112">Für Frameworks, die verwaltete zulassen `x:Code` Inhalte, die richtige Sprachcompiler mit `x:Code` Inhalt richtet sich nach den Einstellungen und Ziele des enthaltenden Projekts, das verwendet wird, um die Anwendung zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ceee3-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="ceee3-113">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="ceee3-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="ceee3-114">In Code deklariert `x:Code` für WPF mehrere wichtige Einschränkungen hat:</span><span class="sxs-lookup"><span data-stu-id="ceee3-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
-   <span data-ttu-id="ceee3-115">Die `x:Code` Anweisungselement muss ein unmittelbar untergeordnetes Element des Stammelements der Verwendung von XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="ceee3-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
-   <span data-ttu-id="ceee3-116">[X: Class-Direktive](../../../docs/framework/xaml-services/x-class-directive.md) muss auf dem übergeordneten Root-Element angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ceee3-116">[x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md) must be provided on the parent root element.</span></span>  
  
-   <span data-ttu-id="ceee3-117">Der Code Hauptvideos `x:Code` behandelt werden, von der Kompilierung innerhalb des Bereichs der partiellen Klasse sein, der bereits für die Verwendung von XAML-Seite erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ceee3-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="ceee3-118">Daher muss alle Code den von Ihnen definierten Member oder Variablen der partiellen Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="ceee3-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
-   <span data-ttu-id="ceee3-119">Sie können keine zusätzliche Klassen definieren, als durch das Schachteln einer Klasse in der partiellen Klasse (Schachtelung ist zulässig, aber es ist nicht typisch, da geschachtelte Klassen in XAML verwiesen werden kann).</span><span class="sxs-lookup"><span data-stu-id="ceee3-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="ceee3-120">CLR-Namespaces als dem, der für die vorhandene partielle Klasse verwendet wird, kann nicht definiert oder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ceee3-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
-   <span data-ttu-id="ceee3-121">Verweise auf Entitäten außerhalb der partiellen Klasse CLR-Namespaces müssen alle vollqualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="ceee3-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="ceee3-122">Wenn Mitglieder, die deklariert wird, überschreibungen, um die partielle Klasse überschreibbaren Membern sind, muss dies mit den sprachspezifischen Override-Schlüsselwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ceee3-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="ceee3-123">Wenn Elemente in deklariert `x:Code` Bereich in Konflikt mit Mitgliedern der partiellen Klasse, die aus der XAML-Code erstellt, so, dass der Compiler den Konflikt, meldet die XAML-Datei kann nicht kompilieren oder geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ceee3-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceee3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceee3-124">See Also</span></span>  
 [<span data-ttu-id="ceee3-125">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ceee3-125">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="ceee3-126">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="ceee3-126">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="ceee3-127">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="ceee3-127">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
