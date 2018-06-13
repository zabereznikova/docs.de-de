---
title: PresentationOptions:Freeze-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546070"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="d9416-102">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="d9416-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="d9416-103">Legt die <xref:System.Windows.Freezable.IsFrozen%2A> Zustand `true` für das enthaltende <xref:System.Windows.Freezable> Element.</span><span class="sxs-lookup"><span data-stu-id="d9416-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="d9416-104">Standardverhalten für eine <xref:System.Windows.Freezable> ohne die `PresentationOptions:Freeze` Attribut angegeben ist, <xref:System.Windows.Freezable.IsFrozen%2A> ist `false` zur Ladezeit und in Abhängigkeit davon Allgemein <xref:System.Windows.Freezable> Verhalten zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="d9416-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d9416-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="d9416-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d9416-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="d9416-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="d9416-107">Ein XML-Namespace-Präfix, der eine beliebige gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation sein kann.</span><span class="sxs-lookup"><span data-stu-id="d9416-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="d9416-108">Das Präfix `PresentationOptions` für Identifikationszwecke in dieser Dokumentation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9416-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="d9416-109">Ein Element, das alle instanziiert abgeleitete Klasse der <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="d9416-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9416-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9416-110">Remarks</span></span>  
 <span data-ttu-id="d9416-111">Die `Freeze` Attribut das einzige Attribut ist oder in anderen Programmierelements definiert die `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="d9416-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="d9416-112">Die `Freeze` Attribut in diesem speziellen Namespace vorhanden ist, insbesondere, damit es als ignorierbares mit festgelegt werden kann [Mc: Ignorierbares Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) als Teil der Stamm-Elementdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="d9416-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="d9416-113">Der Grund, `Freeze` muss in der Lage, ignorierbares werden ist da nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Implementierungen von ereignissprozessoren können so fixieren Sie eine <xref:System.Windows.Freezable> zur Ladezeit; diese Funktion ist nicht Teil der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="d9416-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="d9416-114">Die Möglichkeit zum Verarbeiten der `Freeze` Attribut ist insbesondere in integriert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, der verarbeitet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für kompilierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="d9416-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="d9416-115">Das Attribut wird nicht durch alle Klassen unterstützt, und die Attributsyntax ist nicht erweiterbar oder geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d9416-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="d9416-116">Wenn Sie eine eigene Implementierung von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, Sie können das Fixieren Verhalten des parallel auf, der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor bei der Verarbeitung der `Freeze` -Attribut <xref:System.Windows.Freezable> Elemente zur Ladezeit des.</span><span class="sxs-lookup"><span data-stu-id="d9416-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="d9416-117">Jeder Wert für die `Freeze` außer-Attribut `true` (ohne Beachtung von Groß-/Kleinschreibung), wird ein Ladezeitfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="d9416-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="d9416-118">(Angeben der `Freeze` Attribut `false` ist kein Fehler, aber, der sich bereits die Standardeinstellung, also zu `false` wird keine Aktion ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="d9416-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9416-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9416-119">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="d9416-120">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="d9416-120">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="d9416-121">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="d9416-121">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
