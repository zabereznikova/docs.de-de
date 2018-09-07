---
title: mc:ProcessContent-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 59097959ff4b3efaba4e4ee63d308eb21f91529d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44070094"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="99d58-102">mc:ProcessContent-Attribut</span><span class="sxs-lookup"><span data-stu-id="99d58-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="99d58-103">Gibt an, welche [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Elemente Inhalte werden von entsprechenden übergeordneten Elementen verarbeitet, auch wenn das unmittelbar übergeordnete Element von werden möglicherweise ignoriert immer noch haben sollte eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor aufgrund der Angabe [Mc: Ignorable-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="99d58-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="99d58-104">Die `mc:ProcessContent` Attribut Markupkompatibilität unterstützt, für den benutzerdefinierten Namespace-Zuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="99d58-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="99d58-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="99d58-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="99d58-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="99d58-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99d58-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="99d58-107">*ignorablePrefix*</span></span>|<span data-ttu-id="99d58-108">Jede gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="99d58-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="99d58-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="99d58-109">*ignorableUri*</span></span>|<span data-ttu-id="99d58-110">Ein beliebiger gültiger URI für das Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="99d58-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="99d58-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="99d58-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="99d58-112">Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="99d58-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="99d58-113">*[Inhalt]*</span><span class="sxs-lookup"><span data-stu-id="99d58-113">*[content]*</span></span>|<span data-ttu-id="99d58-114">*ThisElementCanBeIgnored* ignorable markiert ist.</span><span class="sxs-lookup"><span data-stu-id="99d58-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="99d58-115">Wenn der Prozessor über diesem Element ignoriert *[Inhalt]* wird vom *Objekt*.</span><span class="sxs-lookup"><span data-stu-id="99d58-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99d58-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99d58-116">Remarks</span></span>  
 <span data-ttu-id="99d58-117">Standardmäßig eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert den Inhalt in einem Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="99d58-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="99d58-118">Sie können angeben, ein bestimmtes Element von `mc:ProcessContent`, und ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor bleibt der Inhalt innerhalb der Ignoriertes Element verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="99d58-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="99d58-119">Dies wird normalerweise verwendet, wenn der Inhalt innerhalb mehrerer Tags geschachtelt ist, mindestens eine der ignorable und mindestens einer davon nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="99d58-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="99d58-120">Mehrere Präfixe können angegeben werden, in das Attribut mit Leerzeichen als Trennzeichen, z. B.: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="99d58-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="99d58-121">Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die in diesem Bereich nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99d58-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="99d58-122">Weitere Informationen finden Sie unter [XML-Markup-Compatibility-Spezifikation](https://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="99d58-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d58-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99d58-123">See Also</span></span>  
 [<span data-ttu-id="99d58-124">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="99d58-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="99d58-125">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="99d58-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
