---
title: mc:ProcessContent-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bc406659bec3fd8d5da87b597356a3411c7a2605
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567401"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="a1b05-102">mc:ProcessContent-Attribut</span><span class="sxs-lookup"><span data-stu-id="a1b05-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="a1b05-103">Gibt an [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , welche Elemente weiterhin Inhalte haben sollen, die durch relevante übergeordnete Elemente verarbeitet werden sollen, auch wenn das unmittelbare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] übergeordnete Element von einem Prozessor aufgrund der Angabe des [MC: Ignorable-Attributs](mc-ignorable-attribute.md)ignoriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1b05-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="a1b05-104">Das `mc:ProcessContent` Attribut unterstützt Markup Kompatibilität sowohl für die Zuordnung von benutzerdefinierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Namespaces als auch für die Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="a1b05-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a1b05-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="a1b05-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a1b05-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="a1b05-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1b05-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="a1b05-107">*ignorablePrefix*</span></span>|<span data-ttu-id="a1b05-108">Eine beliebige gültige Präfix Zeichenfolge gemäß der XML 1,0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="a1b05-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="a1b05-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="a1b05-109">*ignorableUri*</span></span>|<span data-ttu-id="a1b05-110">Ein beliebiger gültiger URI zum Festlegen eines Namespaces gemäß der XML 1,0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="a1b05-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="a1b05-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="a1b05-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="a1b05-112">Ein Element, das von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Prozessor Implementierungen ignoriert werden kann, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1b05-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="a1b05-113">*inhaltliche*</span><span class="sxs-lookup"><span data-stu-id="a1b05-113">*[content]*</span></span>|<span data-ttu-id="a1b05-114">" *ThisElementCanBeIgnored* " ist als "Ignorable" gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a1b05-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="a1b05-115">Wenn der Prozessor dieses Element ignoriert, wird *[Content]* vom *Objekt*verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a1b05-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1b05-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1b05-116">Remarks</span></span>  
 <span data-ttu-id="a1b05-117">Standardmäßig ignoriert ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Inhalte innerhalb eines ignorierten Elements.</span><span class="sxs-lookup"><span data-stu-id="a1b05-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="a1b05-118">Sie können ein bestimmtes Element mithilfe von `mc:ProcessContent`angeben, und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ein Prozessor verarbeitet den Inhalt weiterhin im ignorierten Element.</span><span class="sxs-lookup"><span data-stu-id="a1b05-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="a1b05-119">Dies wird normalerweise verwendet, wenn der Inhalt in mehreren Tags geschachtelt ist, mindestens einer von einem Ignorable-Element, das nicht Ignorable ist.</span><span class="sxs-lookup"><span data-stu-id="a1b05-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="a1b05-120">Im-Attribut können mehrere Präfixe mit einem Leerzeichen angegeben werden, z. b. `mc:ProcessContent="ignore:Element1 ignore:Element2"`:.</span><span class="sxs-lookup"><span data-stu-id="a1b05-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="a1b05-121">Der [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert andere Elemente und Attribute, die in diesem Bereich des SDK nicht dokumentiert sind.</span><span class="sxs-lookup"><span data-stu-id="a1b05-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="a1b05-122">Weitere Informationen finden Sie unter [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="a1b05-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1b05-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1b05-123">See also</span></span>

- [<span data-ttu-id="a1b05-124">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="a1b05-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="a1b05-125">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a1b05-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
