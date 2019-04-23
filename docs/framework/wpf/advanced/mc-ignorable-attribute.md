---
title: mc:Ignorable-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 03439a2c4a1a4de375e90d0e5121e690541e2f0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219329"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="46bbe-102">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="46bbe-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="46bbe-103">Gibt an, welche [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespacepräfixe, die bei der ein Markup-Datei können ignoriert werden, indem eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor.</span><span class="sxs-lookup"><span data-stu-id="46bbe-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="46bbe-104">Die `mc:Ignorable` Attribut Markupkompatibilität unterstützt, für den benutzerdefinierten Namespace-Zuordnung und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="46bbe-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="46bbe-105">XAML-Attributverwendung (einzelnes Adresspräfix)</span><span class="sxs-lookup"><span data-stu-id="46bbe-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="46bbe-106">XAML-Attributverwendung (zwei Präfixe)</span><span class="sxs-lookup"><span data-stu-id="46bbe-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="46bbe-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="46bbe-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46bbe-108">*ignorablePrefix, ignorablePrefix1, etc.*</span><span class="sxs-lookup"><span data-stu-id="46bbe-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="46bbe-109">Jede gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="46bbe-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="46bbe-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="46bbe-110">*ignorableUri*</span></span>|<span data-ttu-id="46bbe-111">Ein beliebiger gültiger URI für das Angeben eines Namespaces, gemäß der XML 1.0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="46bbe-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="46bbe-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="46bbe-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="46bbe-113">Ein Element, das vom ignoriert werden sollen, kann [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Implementierungen von ereignissprozessoren, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="46bbe-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46bbe-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46bbe-114">Remarks</span></span>  
 <span data-ttu-id="46bbe-115">Die `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace-Präfix ist die empfohlene Präfix-Konvention zu verwenden, wenn die Zuordnung der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Compatibility-Namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46bbe-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="46bbe-116">Elemente oder Attribute, die bei der Präfixteil der Elementname als identifiziert `mc:Ignorable` löst keinen Fehler bei der Verarbeitung durch eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor.</span><span class="sxs-lookup"><span data-stu-id="46bbe-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="46bbe-117">Wenn dieses Attribut nicht in einen zugrunde liegenden Typ oder einen Programmierungskonstrukt aufgelöst werden konnte, wird dieses Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="46bbe-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="46bbe-118">Beachten Sie jedoch, dass das ignorierte Elemente weiterhin zusätzliche Analysefehler für zusätzliche Containerelement-Anforderungen generieren können, die Nebeneffekte des jeweiligen Elements, das nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="46bbe-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="46bbe-119">Z. B. möglicherweise ein bestimmtes Elementinhaltsmodell genau ein untergeordnetes Element, jedoch wenn das angegebene untergeordnete Element in wurde einer `mc:Ignorable` Präfix und das angegebene untergeordnete Element konnte nicht in einen Typ aufgelöst werden und dann die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor möglicherweise ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="46bbe-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="46bbe-120">`mc:Ignorable` gilt nur für den Namespacezuordnungen zu Bezeichnerzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="46bbe-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="46bbe-121">`mc:Ignorable` gilt nicht für Namespacezuordnungen zu Assemblys, die angeben einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespace und eine Assembly (oder standardmäßig auf die ausführbare Datei als Assembly).</span><span class="sxs-lookup"><span data-stu-id="46bbe-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="46bbe-122">Wenn Sie implementieren eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Prozessor, Ihre-prozessorimplementierung muss nicht auslösen, analysieren oder zu Fehlern auf typauflösung für ein Element oder Attribut, das durch ein Präfix qualifiziert wird, die als identifiziert wird bei der Verarbeitung `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="46bbe-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="46bbe-123">Aber die prozessorimplementierung kann weiterhin Ausnahmen auslösen, die sekundäre eines Elements, das beim Laden oder verarbeitet werden resultieren, beispielsweise eine-untergeordnetes Element weiter oben.</span><span class="sxs-lookup"><span data-stu-id="46bbe-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="46bbe-124">Standardmäßig eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert den Inhalt in einem Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="46bbe-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="46bbe-125">Sie können jedoch zusätzlich das Attribut angeben [MC: ProcessContent-Attribut](mc-processcontent-attribute.md), um die kontinuierliche Verarbeitung des Inhalts in einem ignoriert Element vom nächsten verfügbaren übergeordneten Element erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46bbe-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="46bbe-126">Mehrere Präfixe können angegeben werden, in das Attribut, wobei eine oder mehrere Leerzeichen als Trennzeichen, z. B.: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="46bbe-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="46bbe-127">Die [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] -Namespace definiert, andere Elemente und Attribute, die in diesem Bereich nicht dokumentiert sind die [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46bbe-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="46bbe-128">Weitere Informationen finden Sie unter [XML-Markup-Compatibility-Spezifikation](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="46bbe-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bbe-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46bbe-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="46bbe-130">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="46bbe-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="46bbe-131">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="46bbe-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="46bbe-132">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="46bbe-132">Documents in WPF</span></span>](documents-in-wpf.md)
