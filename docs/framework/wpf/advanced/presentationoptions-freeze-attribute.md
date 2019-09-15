---
title: PresentationOptions:Freeze-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991429"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="aefcc-102">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="aefcc-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="aefcc-103">Legt den <xref:System.Windows.Freezable.IsFrozen%2A> Zustand für `true` das enthaltende <xref:System.Windows.Freezable> Element auf fest.</span><span class="sxs-lookup"><span data-stu-id="aefcc-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="aefcc-104">Das Standardverhalten für <xref:System.Windows.Freezable> eine ohne `PresentationOptions:Freeze` das angegebene- `false` Attribut <xref:System.Windows.Freezable.IsFrozen%2A> ist zur Ladezeit und abhängig vom allgemeinen <xref:System.Windows.Freezable> Verhalten zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="aefcc-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="aefcc-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="aefcc-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="aefcc-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="aefcc-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="aefcc-107">Ein XML-Namespace Präfix, bei dem es sich um eine beliebige gültige Präfix Zeichenfolge handeln kann, gemäß XML 1,0</span><span class="sxs-lookup"><span data-stu-id="aefcc-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="aefcc-108">Dieses Präfix `PresentationOptions` wird zu Identifikationszwecken in dieser Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="aefcc-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="aefcc-109">Ein Element, das jede abgeleitete Klasse von <xref:System.Windows.Freezable>instanziiert.</span><span class="sxs-lookup"><span data-stu-id="aefcc-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aefcc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aefcc-110">Remarks</span></span>  
 <span data-ttu-id="aefcc-111">Das `Freeze` -Attribut ist das einzige Attribut oder ein anderes Programmier Element, `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` das im XML-Namespace definiert ist.</span><span class="sxs-lookup"><span data-stu-id="aefcc-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="aefcc-112">Das `Freeze` -Attribut ist in diesem speziellen Namespace speziell vorhanden, sodass es als Ignorable festgelegt werden kann, wobei das [MC: Ignorable-Attribut](mc-ignorable-attribute.md) als Teil der Stamm Element Deklarationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aefcc-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="aefcc-113">Der Grund, `Freeze` Warum ignoriert werden muss, besteht darin, dass nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Implementierungen zur Ladezeit ein <xref:System.Windows.Freezable> Einfrieren können. diese Funktion ist nicht Teil [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="aefcc-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="aefcc-114">Die Möglichkeit, das `Freeze` -Attribut zu verarbeiten, ist speziell in den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor integriert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der für kompilierte Anwendungen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="aefcc-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="aefcc-115">Das Attribut wird von keiner Klasse unterstützt, und die Attribut Syntax ist nicht erweiterbar oder änderbar.</span><span class="sxs-lookup"><span data-stu-id="aefcc-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="aefcc-116">Wenn Sie einen eigenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor implementieren, können Sie auswählen, ob das Einfrieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] des Prozessors beim Verarbeiten des `Freeze` Attributs für <xref:System.Windows.Freezable> Elemente zur Ladezeit parallel durchlaufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="aefcc-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="aefcc-117">Jeder Wert für das `Freeze` -Attribut `true` , der keine Groß-/Kleinschreibung beachtet, generiert einen Lade Zeitfehler.</span><span class="sxs-lookup"><span data-stu-id="aefcc-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="aefcc-118">(Die Angabe `Freeze` des- `false` Attributs als ist kein Fehler, aber dies ist bereits der Standardwert, `false` sodass das Festlegen von auf nichts bewirkt.)</span><span class="sxs-lookup"><span data-stu-id="aefcc-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefcc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aefcc-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="aefcc-120">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="aefcc-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="aefcc-121">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="aefcc-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
