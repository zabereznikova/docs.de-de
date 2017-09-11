---
title: "Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a><span data-ttu-id="3ce39-102">Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement</span><span class="sxs-lookup"><span data-stu-id="3ce39-102">Mitigation: Grid Control&#39;s Space Allocation to Star-columns</span></span>

<span data-ttu-id="3ce39-103">Bei Anwendungen mit .NET Framework 4.7 und höher als Zielplattform ersetzt WPF den Algorithmus, den das <xref:System.Windows.Controls.Grid>-Steuerelement verwendet, um Platz für \*-Spalten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3ce39-103">Starting with applications that the .NET Framework 4.7, WPF replaces the algorithm that the <xref:System.Windows.Controls.Grid> control uses to allocate space to \*-columns.</span></span> 

## <a name="whats-changed"></a><span data-ttu-id="3ce39-104">Neues</span><span class="sxs-lookup"><span data-stu-id="3ce39-104">What's changed</span></span>

<span data-ttu-id="3ce39-105">Der neue Algorithmus behebt mehrere Probleme, die beim alten Algorithmus auftreten:</span><span class="sxs-lookup"><span data-stu-id="3ce39-105">The new algorithm fixes several bugs present in the old algorithm:</span></span>

1. <span data-ttu-id="3ce39-106">Die Gesamtzuweisung an Spalten kann die Breite des Rasters überschreiten.</span><span class="sxs-lookup"><span data-stu-id="3ce39-106">Total allocation to columns can exceed the Grid's width.</span></span> <span data-ttu-id="3ce39-107">Dies kann beim Zuweisen von Platz an eine Spalte geschehen, deren proportionaler Anteil geringer als ihre Mindestgröße ist.</span><span class="sxs-lookup"><span data-stu-id="3ce39-107">This can occur when allocating space to a column whose proportional share is less than its minimum size.</span></span> <span data-ttu-id="3ce39-108">Der Algorithmus weist die Mindestgröße zu, wodurch der für andere Spalten verfügbare Platz verringert wird.</span><span class="sxs-lookup"><span data-stu-id="3ce39-108">The algorithm allocates the minimum size, which decreases the space available to other columns.</span></span> <span data-ttu-id="3ce39-109">Wenn keine zuzuweisenden \*-Spalten mehr vorhanden sind, ist die Gesamtzuweisung zu groß.</span><span class="sxs-lookup"><span data-stu-id="3ce39-109">If there are no \*-columns left to allocate, the total allocation will be too large.</span></span>

1. <span data-ttu-id="3ce39-110">Die Gesamtzuweisung kann die Breite des Rasters unterschreiten.</span><span class="sxs-lookup"><span data-stu-id="3ce39-110">Total allocation can fall short of the Grid's width.</span></span> <span data-ttu-id="3ce39-111">Dies ist das umgekehrte Problem zu Nr. 1, das beim Zuweisen zu einer Spalte auftritt, deren proportionaler Anteil größer als ihre Maximalgröße ist, wenn keine \*-Spalten zum Ausgleich des Über- oder Untermaßes vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3ce39-111">This is the dual problem to #1, arising when allocating to a column whose proportional share is greater than its maximum size, with no \*-columns left to take up the slack.</span></span>

1. <span data-ttu-id="3ce39-112">Zwei \*-Spalten können Zuweisungen erhalten, die nicht proportional zu ihren *-Gewichtungen sind.</span><span class="sxs-lookup"><span data-stu-id="3ce39-112">Two \*-columns can receive allocations not proportional to their -weights.</span></span> <span data-ttu-id="3ce39-113">Dies ist eine mildere Version von Nr. 1/Nr. 2, die beim Zuweisen zu den *-Spalten A, B und C (in dieser Reihenfolge) auftritt, wobei der proportionale Anteil von B gegen deren Min- oder Max-Bedingung verstößt.</span><span class="sxs-lookup"><span data-stu-id="3ce39-113">This is a milder version of #1/#2, arising when allocating to *-columns A, B, and C (in that order), where B's proportional share violates its min (or max) constraint.</span></span> <span data-ttu-id="3ce39-114">Wie oben ändert sich dadurch der für Spalte C zur Verfügung stehende Platz, die proportional eine kleinere (oder größeren) Zuweisung als A erhält.</span><span class="sxs-lookup"><span data-stu-id="3ce39-114">As above, this changes the space available to column C, who gets less (or more) proportional allocation than A did,</span></span>

1. <span data-ttu-id="3ce39-115">Spalten mit extrem hohen Gewichtungen (> 10^298) werden alle behandelt, als ob sie die Gewichtung 10^298 aufwiesen.</span><span class="sxs-lookup"><span data-stu-id="3ce39-115">Columns with extremely large weights (> 10^298) are all treated as if they had weight 10^298.</span></span> <span data-ttu-id="3ce39-116">Proportionale Unterschiede zwischen ihnen (und zwischen Spalten mit erheblich kleineren Gewichtungen) werden nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="3ce39-116">Proportional differences between them (and between columns with slightly smaller weights) are not honored.</span></span>

1. <span data-ttu-id="3ce39-117">Spalten mit der Gewichtung unendlich werden nicht ordnungsgemäß behandelt.</span><span class="sxs-lookup"><span data-stu-id="3ce39-117">Columns with infinite weights are not handled correctly.</span></span> <span data-ttu-id="3ce39-118">[Tatsächlich lässt sich die Gewichtung nicht auf unendlich festlegen, aber das ist eine künstliche Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="3ce39-118">[Actually you can't set a weight to Infinity, but this is an artificial restriction.</span></span> <span data-ttu-id="3ce39-119">Der Zuweisungscode hat versucht, das Problem zu behandeln, dabei aber versagt.]</span><span class="sxs-lookup"><span data-stu-id="3ce39-119">The allocation code was trying to handle it, but doing a bad job.]</span></span>

1. <span data-ttu-id="3ce39-120">Mehrere kleinere Probleme beim Vermeiden von Überlauf, Unterlauf, Genauigkeitsverlust und ähnlichen Gleitkommaproblemen.</span><span class="sxs-lookup"><span data-stu-id="3ce39-120">Several minor problems while avoiding overflow, underflow, loss of precision and similar floating-point issues.</span></span>

1. <span data-ttu-id="3ce39-121">Anpassungen für Layoutglättung sind bei ausreichend hohem DPI fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="3ce39-121">Adjustments for layout rounding are incorrect at sufficiently high DPI.</span></span>

<span data-ttu-id="3ce39-122">Der neue Algorithmus erzeugt Ergebnisse, die den folgenden Kriterien genügen:</span><span class="sxs-lookup"><span data-stu-id="3ce39-122">The new algorithm produces results that meet the following criteria:</span></span>

<span data-ttu-id="3ce39-123">A.</span><span class="sxs-lookup"><span data-stu-id="3ce39-123">A.</span></span> <span data-ttu-id="3ce39-124">Die einer *-Spalte zugewiesene Breite ist niemals kleiner als ihre Mindestbreite oder größer als ihre Maximalbreite.</span><span class="sxs-lookup"><span data-stu-id="3ce39-124">The actual width assigned to a *-column is never less than its minimum width nor greater than its maximum width.</span></span>

<span data-ttu-id="3ce39-125">B.</span><span class="sxs-lookup"><span data-stu-id="3ce39-125">B.</span></span> <span data-ttu-id="3ce39-126">Jede *-Spalte, der nicht ihre Mindest- oder Maximalbreite zugewiesen wird, wird eine Breite zugewiesen, die proportional zu ihrer *-Gewichtung ist.</span><span class="sxs-lookup"><span data-stu-id="3ce39-126">Each -column that is not assigned its minimum or maximum width is assigned a width proportional to its -weight.</span></span> <span data-ttu-id="3ce39-127">Genauer gesagt, wenn zwei Spalten die Breite x bzw. y zugewiesen werden und keine der beiden Spalten ihre Minimal- oder Maximalbreite erhält, stehen die den Spalten zugewiesenen tatsächlichen Breiten v und w im gleichen Verhältnis: v / w == x / y.</span><span class="sxs-lookup"><span data-stu-id="3ce39-127">To be precise, if two columns are declared with width x and y respectively, and if neither column receives its minimum or maximum width, the actual widths v and w assigned to the columns are in the same proportion: v / w == x / y.</span></span>

<span data-ttu-id="3ce39-128">C.</span><span class="sxs-lookup"><span data-stu-id="3ce39-128">C.</span></span> <span data-ttu-id="3ce39-129">Die Gesamtbreite, die den „proportionalen“ \*-Spalten zugewiesen wird, entspricht dem verfügbaren Platz nach der Zuweisung an die Spalten, die Bedingungen unterliegen (feste Spalten, Spalten mit automatischer Breite und \*-Spalten, denen die Minimal- oder Maximalbreite zugewiesen wird).</span><span class="sxs-lookup"><span data-stu-id="3ce39-129">The total width allocated to "proportional" \*-columns is equal to the space available after allocating to the constrained columns (fixed, auto, and \*-columns that are allocated their min or max width).</span></span> <span data-ttu-id="3ce39-130">Diese kann Null sein, beispielsweise, wenn die Summe der Mindestbreiten die zur Verfügung stehende Breite des Rasters überschreitet.</span><span class="sxs-lookup"><span data-stu-id="3ce39-130">This might be zero, for instance if the sum of the minimum widths exceeds the Grid's availbable width.</span></span>

<span data-ttu-id="3ce39-131">D.</span><span class="sxs-lookup"><span data-stu-id="3ce39-131">D.</span></span> <span data-ttu-id="3ce39-132">Alle diese Anweisungen müssen im Hinblick auf das „ideale“ Layout interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ce39-132">All these statements are to be interpreted with respect to the "ideal" layout.</span></span> <span data-ttu-id="3ce39-133">Wenn Layoutglättung aktiviert ist, können die tatsächlichen Breiten um bis zu ein Pixel von den idealen Breiten abweichen.</span><span class="sxs-lookup"><span data-stu-id="3ce39-133">When layout rounding is in effect, the actual widths can differ from the ideal widths by as much as one pixel.</span></span>

<span data-ttu-id="3ce39-134">Der alte Algorithmus berücksichtigte in den oben dargestellten Fällen (A), nicht jedoch die anderen Kriterien.</span><span class="sxs-lookup"><span data-stu-id="3ce39-134">The old algorithm honored (A) but failed to honor the other criteria in the cases outlined above.</span></span>

<span data-ttu-id="3ce39-135">Alle Aussagen über Spalten und Breite in diesem Thema gelten ebenso für Zeilen und Höhe.</span><span class="sxs-lookup"><span data-stu-id="3ce39-135">Everything said about columns and widths in this topic applies as well to rows and heights.</span></span>

## <a name="impact"></a><span data-ttu-id="3ce39-136">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="3ce39-136">Impact</span></span>

<span data-ttu-id="3ce39-137">Der neue Algorithmus ändert die den \*-Spalten zugewiesene tatsächliche Breite in einer Reihe von Fällen:</span><span class="sxs-lookup"><span data-stu-id="3ce39-137">The new algorithm changes the actual width assigned to \*-columns in a number of cases:</span></span>

- <span data-ttu-id="3ce39-138">Wenn eine oder mehrere \*-Spalten außerdem eine Minimal- oder Maximalbreite aufweisen, die die proportionale Zuweisung für die betreffende Spalte außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="3ce39-138">When one or more \*-columns also have a minimum or maximum width that overrides the proportional allocation for that column.</span></span> <span data-ttu-id="3ce39-139">(Die Minimalbreite kann aus einer expliziten <xref:System.Windows.FrameworkElement.MinWidth%2A>-Deklaration oder aus einem impliziten Minimalwert abgeleitet werden, der sich aus dem Spalteninhalt ergibt.</span><span class="sxs-lookup"><span data-stu-id="3ce39-139">(The minimum width can derive from an explicit <xref:System.Windows.FrameworkElement.MinWidth%2A> declaration, or from an implicit minimum obtained from the column's content.</span></span> <span data-ttu-id="3ce39-140">Die maximale Breite kann nur explizit aus einer <xref:System.Windows.FrameworkElement.MaxWidth%2A>-Deklaration definiert werden.)</span><span class="sxs-lookup"><span data-stu-id="3ce39-140">The maximum width can only be defined explicitly, from a <xref:System.Windows.FrameworkElement.MaxWidth%2A> declaration.)</span></span>

- <span data-ttu-id="3ce39-141">Wenn eine oder mehrere \*-Spalten eine extrem große \*-Gewichtung deklarieren, größer als 10^298.</span><span class="sxs-lookup"><span data-stu-id="3ce39-141">When one or more \*-columns declare an extremely large \*-weight, greater than 10^298.</span></span>

- <span data-ttu-id="3ce39-142">Wenn die \*-Gewichtungen ausreichend verschieden sind, um zu Gleitkommainstabilität zu führen (Überlauf, Unterlauf, Genauigkeitsverlust).</span><span class="sxs-lookup"><span data-stu-id="3ce39-142">When the \*-weights are sufficiently different to encounter floating-point instability (overflow, underflow, loss of precision).</span></span>

- <span data-ttu-id="3ce39-143">Wenn Layoutglättung aktiviert ist und der effektive DPI-Wert der Anzeige ausreichend hoch ist.</span><span class="sxs-lookup"><span data-stu-id="3ce39-143">When layout rounding is enabled, and the effective display DPI is sufficiently high.</span></span>

<span data-ttu-id="3ce39-144">In den beiden ersten Fällen können sich die vom neuen Algorithmus erzeugten Breiten erheblich von den durch den alten Algorithmus erzeugten unterscheiden; im letzten Fall beträgt der Unterschied höchstens ein oder zwei Pixel.</span><span class="sxs-lookup"><span data-stu-id="3ce39-144">In the first two cases, the widths produced by the new algorithm can be significantly different from those produced by the old algorithm; in the last case, the difference will be at most one or two pixels.</span></span>

## <a name="mitigation"></a><span data-ttu-id="3ce39-145">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="3ce39-145">Mitigation</span></span>

<span data-ttu-id="3ce39-146">Standardmäßig verwenden Apps mit einer .NET Framework-Zielplattform ab .NET Framework 4.7 den neuen Algorithmus, während Apps mit der Zielplattform .NET Framework 4.6.2 oder früher den alten Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ce39-146">By default, apps that target versions of the .NET Framework starting with the .NET Framework 4.7 will use the new algorithm, while apps that target the .NET Framework 4.6.2 or earlier versions will use the old algorithm.</span></span>

<span data-ttu-id="3ce39-147">Um die Standardeinstellung außer Kraft zu setzen, verwenden Sie die folgenden Konfigurationseinstellung:</span><span class="sxs-lookup"><span data-stu-id="3ce39-147">To override the default, use the following configuration setting:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

<span data-ttu-id="3ce39-148">Der Wert „true“ legt den alten Algorithmus fest, „false“ den neuen.</span><span class="sxs-lookup"><span data-stu-id="3ce39-148">The value 'true' selects the old algorithm, and 'false' selects the new algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ce39-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ce39-149">See also</span></span>
[<span data-ttu-id="3ce39-150">Änderungen der Neuzuweisungen in .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="3ce39-150">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

