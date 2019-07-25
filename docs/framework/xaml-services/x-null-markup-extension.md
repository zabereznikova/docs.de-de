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
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484707"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="d63c2-102">x:Null-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="d63c2-102">x:Null Markup Extension</span></span>
<span data-ttu-id="d63c2-103">Gibt `null` als Wert für ein XAML-Element an.</span><span class="sxs-lookup"><span data-stu-id="d63c2-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d63c2-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="d63c2-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="d63c2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d63c2-105">Remarks</span></span>  
 <span data-ttu-id="d63c2-106">Das Schlüsselwort für einen NULL- C# Verweis C++ in und ist NULL.</span><span class="sxs-lookup"><span data-stu-id="d63c2-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="d63c2-107">Das Microsoft Visual Basic-Schlüsselwort für einen NULL `Nothing`-Verweis ist, Sie `{x:Null}` verwenden jedoch immer als XAML-Verwendung, unabhängig davon, welche Code Behind-Sprache Sie der XAML zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d63c2-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="d63c2-108">Die `x:Null` Markup Erweiterung hat keine festleg baren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d63c2-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="d63c2-109">Eine null-Verwendung ist häufig dem XAML-Element zugeordnet, das einen CLR <xref:System.Nullable%601> -Wert verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="d63c2-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="d63c2-110">Die `x:Null` Markup Erweiterung verwendet, wie alle XAML-Markup Erweiterungen, die geschweiften Klammern (`{,}`), um die Behandlung von Attributwerten als Literale oder ereignishandlerverweise zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d63c2-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="d63c2-111">Die Attribut Syntax ist die Syntax, die in dieser Markup Erweiterung am häufigsten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d63c2-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="d63c2-112">Eine Objekt Element Syntax `<x:Null />` ist technisch möglich, wird jedoch nur selten verwendet, `x:Null` da die Markup Erweiterung keine Positions Parameter oder Konstruktions Argumente aufweist.</span><span class="sxs-lookup"><span data-stu-id="d63c2-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="d63c2-113">Weitere Informationen zu Markup Erweiterungen finden Sie unter [Markup Erweiterungen und WPF-XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d63c2-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="d63c2-114">In .NET Framework XAML-Diensten wird die Behandlung dieser Markup Erweiterung durch die <xref:System.Windows.Markup.NullExtension> -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="d63c2-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="d63c2-115">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="d63c2-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="d63c2-116">Beachten Sie `null` , dass nicht notwendigerweise der anfängliche nicht festgelegte Wert für eine Verweistyp-Abhängigkeits Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="d63c2-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="d63c2-117">Der anfängliche Standardwert kann für jede Abhängigkeits Eigenschaft variieren und kann auf Eigenschafts spezifischen Metadaten basieren.</span><span class="sxs-lookup"><span data-stu-id="d63c2-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="d63c2-118">Viele Abhängigkeits Eigenschaften akzeptieren `null` aufgrund ihrer Validierungs Rückruf Implementierungen nicht als Wert, entweder durch Markup oder Code.</span><span class="sxs-lookup"><span data-stu-id="d63c2-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="d63c2-119">Weitere Informationen zu Abhängigkeits Eigenschaften finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d63c2-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d63c2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d63c2-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="d63c2-121">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d63c2-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="d63c2-122">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="d63c2-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
