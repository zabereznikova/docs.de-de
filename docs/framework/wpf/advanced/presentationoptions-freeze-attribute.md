---
title: PresentationOptions:Freeze-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074656"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="5ad79-102">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="5ad79-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="5ad79-103">Legt die <xref:System.Windows.Freezable.IsFrozen%2A> Zustand `true` auf dem mit <xref:System.Windows.Freezable> Element.</span><span class="sxs-lookup"><span data-stu-id="5ad79-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="5ad79-104">Standardverhalten für eine <xref:System.Windows.Freezable> ohne die `PresentationOptions:Freeze` Attribut angegeben ist, das <xref:System.Windows.Freezable.IsFrozen%2A> ist `false` am Serverantwortzeiten, Seitenladezeiten und abhängig davon, allgemeine <xref:System.Windows.Freezable> Verhalten zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5ad79-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="5ad79-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="5ad79-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5ad79-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="5ad79-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="5ad79-107">Ein XML-Namespace-Präfix, das eine beliebige Zeichenfolge gültiges Präfix gemäß der XML 1.0-Spezifikation werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ad79-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="5ad79-108">Das Präfix `PresentationOptions` zu Identifikationszwecken in dieser Dokumentation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ad79-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="5ad79-109">Ein Element aus, die instanziiert wird, eine abgeleitete Klasse von <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="5ad79-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ad79-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ad79-110">Remarks</span></span>  
 <span data-ttu-id="5ad79-111">Die `Freeze` Attribut das einzige Attribut ist oder anderen Programmierelements definiert, der `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="5ad79-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="5ad79-112">Die `Freeze` Attribut in diesem speziellen Namespace vorhanden ist, insbesondere, damit es als ignorierbar bezeichnet werden kann [Mc: Ignorable-Attribut](mc-ignorable-attribute.md) als Teil der Stamm-Elementdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="5ad79-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="5ad79-113">Der Grund, `Freeze` muss in der Lage, ignoriert werden ist da nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Implementierungen von ereignissprozessoren können so fixieren Sie einen <xref:System.Windows.Freezable> zur Ladezeit; diese Funktion ist nicht Teil der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="5ad79-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="5ad79-114">Die Möglichkeit zum Verarbeiten der `Freeze` Attribut ist insbesondere in integriert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, der verarbeitet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für kompilierten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="5ad79-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="5ad79-115">Das Attribut wird nicht unterstützt, von jeder Klasse, und die Attributsyntax ist nicht erweiterbar und können geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ad79-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="5ad79-116">Wenn Sie Ihre eigenen implementieren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, Sie können auch das Einfrieren Verhalten der parallele, der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor bei der Verarbeitung der `Freeze` -Attribut <xref:System.Windows.Freezable> Elemente zur Ladezeit.</span><span class="sxs-lookup"><span data-stu-id="5ad79-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="5ad79-117">Jeder Wert für die `Freeze` -Attribut ausschließlich `true` (ohne Beachtung von Groß-/Kleinschreibung), wird eine Ladezeitfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="5ad79-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="5ad79-118">(Angeben der `Freeze` als Attribut `false` ist kein Fehler, aber, der sich bereits die Standardeinstellung, also zum `false` führt keine Aktion).</span><span class="sxs-lookup"><span data-stu-id="5ad79-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad79-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ad79-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="5ad79-120">Übersicht über Freezable-Objekte</span><span class="sxs-lookup"><span data-stu-id="5ad79-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="5ad79-121">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="5ad79-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
