---
title: mc:Ignorable-Attribut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9767b721321b34030a2f276a90c618c658645207
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="f8fbf-102">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="f8fbf-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="f8fbf-103">Gibt an, welche [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacepräfixe, die in einer Markupdatei gefunden können ignoriert werden, indem eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="f8fbf-104">Die `mc:Ignorable` Attribut unterstützt Markupkompatibilität für benutzerdefinierte Namespacezuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="f8fbf-105">Verwendung von XAML-Attributen (Präfix)</span><span class="sxs-lookup"><span data-stu-id="f8fbf-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="f8fbf-106">Verwendung von XAML-Attributen (zwei Präfixe)</span><span class="sxs-lookup"><span data-stu-id="f8fbf-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f8fbf-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="f8fbf-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8fbf-108">*IgnorablePrefix, ignorablePrefix1 usw..*</span><span class="sxs-lookup"><span data-stu-id="f8fbf-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="f8fbf-109">Jede gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="f8fbf-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="f8fbf-110">*ignorableUri*</span></span>|<span data-ttu-id="f8fbf-111">Ein beliebiger gültiger URI zum Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="f8fbf-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="f8fbf-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="f8fbf-113">Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8fbf-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8fbf-114">Remarks</span></span>  
 <span data-ttu-id="f8fbf-115">Die `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacepräfix ist die empfohlene Präfix Konvention, die zu verwendende Zuordnung der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Kompatibilität Namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8fbf-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="f8fbf-116">Elemente oder Attribute, in denen die Präfixteil des Elementnamens als prognostiziert `mc:Ignorable` löst keine Fehler bei der Verarbeitung einer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="f8fbf-117">Wenn dieses Attribut nicht in einen zugrunde liegenden Typ oder einen Programmiermodell aufgelöst werden konnte, wird dieses Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="f8fbf-118">Beachten Sie jedoch, dass ignorierter Elemente möglicherweise noch weitere Analysefehler für zusätzliche Element Anforderungen generiert, die Nebeneffekte des jeweiligen Elements, das nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="f8fbf-119">Beispielsweise kann ein bestimmtes Elementinhaltsmodell erfordern genau ein untergeordnetes Element, wenn das angegebene untergeordnete Element in wurde einer `mc:Ignorable` Präfix und das angegebene untergeordnete Element konnte nicht in einen Typ aufgelöst werden und dann die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor möglicherweise ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="f8fbf-120">`mc:Ignorable`gilt nur für Namespacezuordnungen in Bezeichnerzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="f8fbf-121">`mc:Ignorable`gilt nicht für Namespacezuordnungen, die in Assemblys, die angeben einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespace und eine Assembly (oder standardmäßig auf die aktuelle ausführbare Datei, wie die Assembly befinden).</span><span class="sxs-lookup"><span data-stu-id="f8fbf-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="f8fbf-122">Wenn Sie implementieren eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, wird Ihre-prozessorimplementierung muss nicht ausgelöst, analysieren oder Verarbeitungsfehlern auf typauflösung für ein Element oder Attribut, das durch ein Präfix gekennzeichnet werden, die als identifiziert wird `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="f8fbf-123">Aber Ihre-prozessorimplementierung kann weiterhin, die ein sekundäres Ergebnis eines Elements, das wegen eines Fehlers beim Laden oder verarbeitet werden, z. B. das ein untergeordnetes Element Beispiel weiter oben genannten Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="f8fbf-124">Wird standardmäßig ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert Inhalte innerhalb eines Elements wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="f8fbf-125">Sie können jedoch ein zusätzliches Attribut angeben [MC: ProcessContent Attribut](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), kontinuierliche Verarbeitung von Inhalten innerhalb eines ignorierten Elements vom nächsten verfügbaren übergeordneten Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="f8fbf-126">Mehrere Präfixe können im Attribut, z. B. über eine oder mehrere Leerzeichen als Trennzeichen, angegeben werden: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="f8fbf-126">Multiple prefixes can be specified in the attribute, using one or more whitespace characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  
  
 <span data-ttu-id="f8fbf-127">Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die innerhalb dieses Bereichs, der nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8fbf-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="f8fbf-128">Weitere Informationen finden Sie unter [Kompatibilität-Spezifikation für XML-Markup](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="f8fbf-128">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fbf-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8fbf-129">See Also</span></span>  
 <xref:System.Windows.Markup.XamlReader>  
 [<span data-ttu-id="f8fbf-130">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="f8fbf-130">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [<span data-ttu-id="f8fbf-131">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="f8fbf-131">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="f8fbf-132">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="f8fbf-132">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
