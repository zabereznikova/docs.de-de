---
title: x:Null-Markuperweiterung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 20
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8f176598db00c57159bf351ea5d9ec428c5c04bc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="e35c0-102">x:Null-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="e35c0-102">x:Null Markup Extension</span></span>
<span data-ttu-id="e35c0-103">Gibt an, `null` als Wert für ein XAML-Element.</span><span class="sxs-lookup"><span data-stu-id="e35c0-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="e35c0-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="e35c0-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="e35c0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e35c0-105">Remarks</span></span>  
 <span data-ttu-id="e35c0-106">Das Schlüsselwort für ein null-Verweis in C# geschrieben und [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] ist null.</span><span class="sxs-lookup"><span data-stu-id="e35c0-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="e35c0-107">Das Microsoft Visual Basic-Schlüsselwort für ein null-Verweis ist `Nothing`, aber Sie verwenden immer `{x:Null}` in XAML, unabhängig davon, welche Code-Behind-Sprache, die Sie mit der XAML-Code zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e35c0-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="e35c0-108">Die `x:Null` Markuperweiterung verfügt über keine konfigurierbaren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e35c0-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="e35c0-109">Eine null-Verwendung ist häufig bei der Verwendung von XAML-Member Offenlegung von einem CLR <xref:System.Nullable%601> Wert.</span><span class="sxs-lookup"><span data-stu-id="e35c0-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="e35c0-110">Die `x:Null` Markuperweiterung, z. B. alle Markuperweiterungen für XAML, verwendet die geschweiften Klammern (`{,}`) für die Behandlung von Attributwerten als Literale oder Ereignishandler Verweise Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="e35c0-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="e35c0-111">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="e35c0-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="e35c0-112">Eine Element-Objektsyntax `<x:Null />` ist technisch zwar möglich, jedoch wird nur selten verwendet werden, da die `x:Null` Markuperweiterung verfügt über keine Positionsparameter oder Konstruktionsargumente.</span><span class="sxs-lookup"><span data-stu-id="e35c0-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="e35c0-113">Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="e35c0-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="e35c0-114">In .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung von definiert die <xref:System.Windows.Markup.NullExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="e35c0-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="e35c0-115">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="e35c0-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="e35c0-116">Beachten Sie, dass `null` ist nicht unbedingt der Festlegung Anfangswert für einen Verweistyp-Abhängigkeitseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e35c0-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="e35c0-117">Der anfängliche Standardwert kann für jede Abhängigkeitseigenschaft unterschiedlich und kann auf eigenschaftenspezifischen Metadaten basieren.</span><span class="sxs-lookup"><span data-stu-id="e35c0-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="e35c0-118">Viele Abhängigkeitseigenschaften akzeptieren keine `null` als Wert entweder über Markup oder-Code aufgrund ihrer rückrufimplementierungen Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="e35c0-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="e35c0-119">Weitere Informationen über Abhängigkeitseigenschaften finden Sie unter [Übersicht über Abhängigkeitseigenschaften](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e35c0-119">For more information about dependency properties, see [Dependency Properties Overview](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35c0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e35c0-120">See Also</span></span>  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [<span data-ttu-id="e35c0-121">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e35c0-121">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="e35c0-122">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="e35c0-122">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
