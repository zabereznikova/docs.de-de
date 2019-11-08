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
ms.openlocfilehash: e14ab0ebc7d44e2792307b16c7c0581ff7a71bc6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740824"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="732fc-102">mc:Ignorable-Attribut</span><span class="sxs-lookup"><span data-stu-id="732fc-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="732fc-103">Gibt an, welche XML-Namespace Präfixe, die in einer Markup Datei vorkommen, von einem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="732fc-103">Specifies which XML namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="732fc-104">Das `mc:Ignorable`-Attribut unterstützt Markup Kompatibilität sowohl für die Zuordnung von benutzerdefinierten Namespaces als auch für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="732fc-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="732fc-105">Verwendung von XAML-Attributen (einzelnes Präfix)</span><span class="sxs-lookup"><span data-stu-id="732fc-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="732fc-106">Verwendung von XAML-Attributen (zwei Präfixe)</span><span class="sxs-lookup"><span data-stu-id="732fc-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="732fc-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="732fc-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="732fc-108">*ignorablePrefix, ignorablePrefix1 usw.*</span><span class="sxs-lookup"><span data-stu-id="732fc-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="732fc-109">Eine beliebige gültige Präfix Zeichenfolge gemäß der XML 1,0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="732fc-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="732fc-110">*ignorableuri*</span><span class="sxs-lookup"><span data-stu-id="732fc-110">*ignorableUri*</span></span>|<span data-ttu-id="732fc-111">Ein beliebiger gültiger URI zum Festlegen eines Namespaces gemäß der XML 1,0-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="732fc-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="732fc-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="732fc-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="732fc-113">Ein Element, das von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Prozessor Implementierungen ignoriert werden kann, wenn der zugrunde liegende Typ nicht aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="732fc-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="732fc-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="732fc-114">Remarks</span></span>  
 <span data-ttu-id="732fc-115">Das `mc` XML-Namespace Präfix ist die empfohlene Präfix Konvention, die beim Mapping des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Compatibility-Namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="732fc-115">The `mc` XML namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`.</span></span>  
  
 <span data-ttu-id="732fc-116">Elemente oder Attribute, bei denen der Präfix Teil des Element namens als `mc:Ignorable` identifiziert wird, werden bei der Verarbeitung durch einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor keine Fehler hervorrufen.</span><span class="sxs-lookup"><span data-stu-id="732fc-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="732fc-117">Wenn dieses Attribut nicht in einen zugrunde liegenden Typ oder ein zugrunde liegendes Programmierkonstrukt aufgelöst werden konnte, wird dieses Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="732fc-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="732fc-118">Beachten Sie jedoch, dass ignorierte Elemente möglicherweise weiterhin zusätzliche Analyse-Fehler für zusätzliche Element Anforderungen generieren, die Nebeneffekte dieses Elements sind, die nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="732fc-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="732fc-119">Beispielsweise kann ein bestimmtes Element Inhalts Modell genau ein untergeordnetes Element erfordern, aber wenn das angegebene untergeordnete Element in einem `mc:Ignorable` Präfix war und das angegebene untergeordnete Element nicht in einen Typ aufgelöst werden konnte, kann der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor einen Fehler hervorrufen.</span><span class="sxs-lookup"><span data-stu-id="732fc-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="732fc-120">`mc:Ignorable` gilt nur für Namespace Zuordnungen zu Bezeichnerzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="732fc-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="732fc-121">`mc:Ignorable` gilt nicht für Namespace Zuordnungen in Assemblys, die einen CLR-Namespace und eine Assembly angeben (oder standardmäßig die aktuelle ausführbare Datei als Assembly).</span><span class="sxs-lookup"><span data-stu-id="732fc-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="732fc-122">Wenn Sie einen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor implementieren, darf die Prozessor Implementierung keine Analyse-oder Verarbeitungsfehler bei der Typauflösung für ein Element oder Attribut, das durch ein als `mc:Ignorable`bezeichnetes Präfix qualifiziert ist, lösen.</span><span class="sxs-lookup"><span data-stu-id="732fc-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="732fc-123">Die Prozessor Implementierung kann jedoch weiterhin Ausnahmen verursachen, bei denen es sich um ein sekundäres Ergebnis eines Elements handelt, das nicht geladen oder verarbeitet werden kann, z. b. das zuvor angegebene Beispiel mit einem untergeordneten Element.</span><span class="sxs-lookup"><span data-stu-id="732fc-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="732fc-124">Standardmäßig ignoriert ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Inhalt innerhalb eines ignorierten Elements.</span><span class="sxs-lookup"><span data-stu-id="732fc-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="732fc-125">Sie können jedoch ein zusätzliches Attribut, [MC: ProcessContent-Attribut](mc-processcontent-attribute.md), angeben, um die fortgesetzte Verarbeitung von Inhalt innerhalb eines ignorierten Elements durch das nächste verfügbare übergeordnete Element zu erfordern.</span><span class="sxs-lookup"><span data-stu-id="732fc-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="732fc-126">Mehrere Präfixe können im-Attribut angegeben werden, wobei mindestens ein Leerzeichen als Trennzeichen verwendet wird, z. b. `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="732fc-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="732fc-127">Der `http://schemas.openxmlformats.org/markup-compatibility/2006`-Namespace definiert andere Elemente und Attribute, die in diesem Bereich des SDK nicht dokumentiert sind.</span><span class="sxs-lookup"><span data-stu-id="732fc-127">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="732fc-128">Weitere Informationen finden Sie unter [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="732fc-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732fc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="732fc-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="732fc-130">PresentationOptions:Freeze-Attribut</span><span class="sxs-lookup"><span data-stu-id="732fc-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="732fc-131">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="732fc-131">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="732fc-132">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="732fc-132">Documents in WPF</span></span>](documents-in-wpf.md)
