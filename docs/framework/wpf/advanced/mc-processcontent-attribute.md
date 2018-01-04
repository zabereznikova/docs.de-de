---
title: mc:ProcessContent-Attribut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fe43e2450c35d976db7a188f854f7864f298afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="013df-102">mc:ProcessContent-Attribut</span><span class="sxs-lookup"><span data-stu-id="013df-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="013df-103">Gibt an, welche [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Elemente sollten Inhalte, die vom entsprechenden übergeordneten Elementen verarbeitet weiterhin bestehen, auch wenn das unmittelbar übergeordnete Element von ignoriert werden kann ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor aufgrund angeben [Mc: Ignorierbares Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="013df-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="013df-104">Die `mc:ProcessContent` Attribut unterstützt Markupkompatibilität für benutzerdefinierte Namespacezuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="013df-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="013df-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="013df-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="013df-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="013df-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="013df-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="013df-107">*ignorablePrefix*</span></span>|<span data-ttu-id="013df-108">Jede gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="013df-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="013df-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="013df-109">*ignorableUri*</span></span>|<span data-ttu-id="013df-110">Ein beliebiger gültiger URI zum Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="013df-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="013df-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="013df-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="013df-112">Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="013df-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="013df-113">*[Content]*</span><span class="sxs-lookup"><span data-stu-id="013df-113">*[content]*</span></span>|<span data-ttu-id="013df-114">*ThisElementCanBeIgnored* ignorierbares gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="013df-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="013df-115">Wenn der Prozessor dieses Element ignoriert *[Inhalt]* wird verarbeitet, indem *Objekt*.</span><span class="sxs-lookup"><span data-stu-id="013df-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="013df-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="013df-116">Remarks</span></span>  
 <span data-ttu-id="013df-117">Wird standardmäßig ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert Inhalte innerhalb eines Elements wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="013df-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="013df-118">Sie können ein bestimmtes Element durch angeben `mc:ProcessContent`, und ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verarbeitet weiterhin den Inhalt innerhalb des Elements wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="013df-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="013df-119">Dies wird normalerweise verwendet, wenn der Inhalt innerhalb mehrerer Tags geschachtelt ist, mindestens eine der ignorierbares und mindestens eine der nicht ignoriert.</span><span class="sxs-lookup"><span data-stu-id="013df-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="013df-120">Mehrere Präfixe können angegeben werden, in das Attribut mit Leerzeichen als Trennzeichen, z. B.: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span><span class="sxs-lookup"><span data-stu-id="013df-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="013df-121">Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die innerhalb dieses Bereichs, der nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="013df-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="013df-122">Weitere Informationen finden Sie unter [Kompatibilität-Spezifikation für XML-Markup](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="013df-122">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013df-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="013df-123">See Also</span></span>  
 [<span data-ttu-id="013df-124">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="013df-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="013df-125">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="013df-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
