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
ms.openlocfilehash: f4971d61d11ec14eaeac2d2f202353e4921b9325
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549443"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="87b6a-102">x:Null-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="87b6a-102">x:Null Markup Extension</span></span>

<span data-ttu-id="87b6a-103">Gibt `null` als Wert für ein XAML-Element an.</span><span class="sxs-lookup"><span data-stu-id="87b6a-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="87b6a-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="87b6a-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="87b6a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87b6a-105">Remarks</span></span>

<span data-ttu-id="87b6a-106">Das Schlüsselwort für einen NULL-Verweis in c# und C++ ist NULL.</span><span class="sxs-lookup"><span data-stu-id="87b6a-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="87b6a-107">Das Microsoft Visual Basic-Schlüsselwort für einen NULL-Verweis ist `Nothing` , Sie verwenden jedoch immer `{x:Null}` als XAML-Verwendung, unabhängig davon, welche Code Behind-Sprache Sie der XAML zuordnen.</span><span class="sxs-lookup"><span data-stu-id="87b6a-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="87b6a-108">Die `x:Null` Markup Erweiterung hat keine festleg baren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="87b6a-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="87b6a-109">Eine null-Verwendung ist häufig dem XAML-Element zugeordnet, das einen CLR-Wert verfügbar macht <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="87b6a-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="87b6a-110">Die `x:Null` Markup Erweiterung verwendet, wie alle XAML-Markup Erweiterungen, die geschweiften Klammern (), um `{,}` die Behandlung von Attributwerten als Literale oder ereignishandlerverweise zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="87b6a-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="87b6a-111">Die Attribut Syntax ist die Syntax, die in dieser Markup Erweiterung am häufigsten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87b6a-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="87b6a-112">Eine Objekt Element Syntax `<x:Null />` ist technisch möglich, wird jedoch nur selten verwendet, da die `x:Null` Markup Erweiterung keine Positions Parameter oder Konstruktions Argumente aufweist.</span><span class="sxs-lookup"><span data-stu-id="87b6a-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="87b6a-113">Weitere Informationen zu Markup Erweiterungen finden Sie unter [Markup Erweiterungen und WPF-XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span><span class="sxs-lookup"><span data-stu-id="87b6a-113">For information about markup extensions, see [Markup Extensions and WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span></span>

<span data-ttu-id="87b6a-114">In .net XAML-Diensten wird die Behandlung dieser Markup Erweiterung durch die- <xref:System.Windows.Markup.NullExtension> Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="87b6a-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="87b6a-115">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="87b6a-115">WPF Usage Notes</span></span>

<span data-ttu-id="87b6a-116">Beachten Sie, dass `null` nicht notwendigerweise der anfängliche nicht festgelegte Wert für eine Verweistyp-Abhängigkeits Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="87b6a-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="87b6a-117">Der anfängliche Standardwert kann für jede Abhängigkeits Eigenschaft variieren und kann auf Eigenschafts spezifischen Metadaten basieren.</span><span class="sxs-lookup"><span data-stu-id="87b6a-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="87b6a-118">Viele Abhängigkeits Eigenschaften akzeptieren `null` aufgrund ihrer Validierungs Rückruf Implementierungen nicht als Wert, entweder durch Markup oder Code.</span><span class="sxs-lookup"><span data-stu-id="87b6a-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="87b6a-119">Weitere Informationen zu Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span><span class="sxs-lookup"><span data-stu-id="87b6a-119">For more information about dependency properties, see [Dependency Properties Overview](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="87b6a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87b6a-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="87b6a-121">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="87b6a-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="87b6a-122">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="87b6a-122">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)
