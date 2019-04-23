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
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100807"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="b05f2-102">x:Null-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="b05f2-102">x:Null Markup Extension</span></span>
<span data-ttu-id="b05f2-103">Gibt an, `null` als Wert für ein XAML-Element.</span><span class="sxs-lookup"><span data-stu-id="b05f2-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b05f2-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="b05f2-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="b05f2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b05f2-105">Remarks</span></span>  
 <span data-ttu-id="b05f2-106">Das Schlüsselwort für ein null-Verweis in C# und [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] ist null.</span><span class="sxs-lookup"><span data-stu-id="b05f2-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="b05f2-107">Das Microsoft Visual Basic-Schlüsselwort für ein null-Verweis ist `Nothing`, aber Sie verwenden immer `{x:Null}` wie die XAML-Nutzung unabhängig davon, welcher Code-Behind-Sprache, die Sie mit der XAML verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="b05f2-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="b05f2-108">Die `x:Null` Markuperweiterung hat keine festlegbaren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b05f2-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="b05f2-109">Eine null-Verwendung ist häufig die XAML-Member-Offenlegung von CLR zugeordnet <xref:System.Nullable%601> Wert.</span><span class="sxs-lookup"><span data-stu-id="b05f2-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="b05f2-110">Die `x:Null` Markuperweiterung, z. B. alle Markuperweiterungen für XAML, verwendet die geschweiften Klammern (`{,}`) für die Behandlung von Attributwerten als Literale oder Ereignishandler-Verweise werden Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="b05f2-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="b05f2-111">Die Attributsyntax ist die Syntax, die mit dieser Markuperweiterung am häufigsten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b05f2-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="b05f2-112">Ein Objektelement-Syntax `<x:Null />` ist technisch möglich, jedoch wird nur selten verwendet werden, da die `x:Null` Markuperweiterung verfügt über keine Positionsparameter oder Konstruktionsargumente.</span><span class="sxs-lookup"><span data-stu-id="b05f2-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="b05f2-113">Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="b05f2-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="b05f2-114">In .NET Framework-XAML-Dienste, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.NullExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b05f2-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="b05f2-115">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="b05f2-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="b05f2-116">Beachten Sie, dass `null` ist nicht unbedingt der Anfangswert für eine Abhängigkeitseigenschaft vom Verweistyp nicht festgelegte.</span><span class="sxs-lookup"><span data-stu-id="b05f2-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="b05f2-117">Der anfängliche Standardwert kann für jede Abhängigkeitseigenschaft unterschiedlich sein und kann basierend auf Metadaten.</span><span class="sxs-lookup"><span data-stu-id="b05f2-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="b05f2-118">Viele Abhängigkeitseigenschaften akzeptieren keine `null` als Wert entweder über Markup oder Code aufgrund ihrer rückrufimplementierungen Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="b05f2-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="b05f2-119">Weitere Informationen zu Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b05f2-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05f2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b05f2-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="b05f2-121">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="b05f2-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="b05f2-122">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="b05f2-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
