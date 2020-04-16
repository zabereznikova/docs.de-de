---
title: x:Null-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432695"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="2461a-102">x:Null-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="2461a-102">x:Null Markup Extension</span></span>

<span data-ttu-id="2461a-103">Gibt `null` als Wert für ein XAML-Element an.</span><span class="sxs-lookup"><span data-stu-id="2461a-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="2461a-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="2461a-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="2461a-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2461a-105">Remarks</span></span>

<span data-ttu-id="2461a-106">Das Schlüsselwort für einen Nullverweis in C- und C++ ist null.</span><span class="sxs-lookup"><span data-stu-id="2461a-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="2461a-107">Das Microsoft Visual Basic-Schlüsselwort `Nothing`für einen `{x:Null}` Nullverweis ist , sie verwenden jedoch immer als XAML-Verwendung, unabhängig davon, welche CodeBehind-Sprache Sie dem XAML zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2461a-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="2461a-108">Die `x:Null` Markuperweiterung hat keine festsetzbaren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="2461a-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="2461a-109">Eine Nullverwendung ist häufig mit der XAML-Member-Exposition eines CLR-Werts <xref:System.Nullable%601> verknüpft.</span><span class="sxs-lookup"><span data-stu-id="2461a-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="2461a-110">Die `x:Null` Markuperweiterung verwendet, wie alle XAML-Markuperweiterungen, die geschweiften Klammern (`{,}`), um der Verarbeitung von Attributwerten zu entgehen, die nicht als Literale oder Ereignishandlerverweise gelten.</span><span class="sxs-lookup"><span data-stu-id="2461a-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="2461a-111">Attributsyntax ist die Syntax, die am häufigsten mit dieser Markuperweiterung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2461a-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="2461a-112">Eine Objektelementsyntax `<x:Null />` ist technisch möglich, wird `x:Null` aber nur selten verwendet, da die Markuperweiterung keine Positionsparameter oder Konstruktionsargumente aufweist.</span><span class="sxs-lookup"><span data-stu-id="2461a-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="2461a-113">Informationen zu Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="2461a-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="2461a-114">In .NET XAML Services wird die Verarbeitung für <xref:System.Windows.Markup.NullExtension> diese Markuperweiterung durch die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="2461a-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="2461a-115">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="2461a-115">WPF Usage Notes</span></span>

<span data-ttu-id="2461a-116">Beachten `null` Sie, dass dies nicht unbedingt der anfängliche Nichtsetwert für eine Abhängigkeitseigenschaft des Referenztyps ist.</span><span class="sxs-lookup"><span data-stu-id="2461a-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="2461a-117">Der anfängliche Standardwert kann für jede Abhängigkeitseigenschaft variieren und auf eigenschaftsspezifischen Metadaten basieren.</span><span class="sxs-lookup"><span data-stu-id="2461a-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="2461a-118">Viele Abhängigkeitseigenschaften `null` akzeptieren aufgrund ihrer Validierungsrückrufimplementierungen weder durch Markup noch über Code einen Wert.</span><span class="sxs-lookup"><span data-stu-id="2461a-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="2461a-119">Weitere Informationen zu Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2461a-119">For more information about dependency properties, see [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2461a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2461a-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="2461a-121">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="2461a-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="2461a-122">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="2461a-122">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
