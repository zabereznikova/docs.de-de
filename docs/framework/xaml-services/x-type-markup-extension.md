---
title: x:Type-Markuperweiterung
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
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db56c2bcdca14b87de320dfe19a6c364c76ecef7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="ceb33-102">x:Type-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="ceb33-102">x:Type Markup Extension</span></span>
<span data-ttu-id="ceb33-103">Die CLR stellt <xref:System.Type> Objekt, das den zugrunde liegenden Typ für einen angegebenen XAML-Typ ist.</span><span class="sxs-lookup"><span data-stu-id="ceb33-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ceb33-104">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="ceb33-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="ceb33-105">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="ceb33-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ceb33-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="ceb33-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="ceb33-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ceb33-107">Optional.</span></span> <span data-ttu-id="ceb33-108">Ein Präfix, das einen nicht standardmäßigen XAML-Namespace zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ceb33-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="ceb33-109">Angeben eines Präfix ist häufig nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ceb33-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="ceb33-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="ceb33-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="ceb33-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ceb33-111">Required.</span></span> <span data-ttu-id="ceb33-112">Ein Typname der aktuellen XAML-Standardnamespace; oder das angegebene Präfix Wenn `prefix` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ceb33-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceb33-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ceb33-113">Remarks</span></span>  
 <span data-ttu-id="ceb33-114">Die `x:Type` Markuperweiterung hat eine ähnliche Funktion, die `typeof()` Operator in c# oder der `GetType` Operator in Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ceb33-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>  
  
 <span data-ttu-id="ceb33-115">Die `x:Type` Markuperweiterung gibt das Konvertierungsverhalten from-Zeichenfolgen für Eigenschaften, die der Typ akzeptieren <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="ceb33-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="ceb33-116">Die Eingabe ist ein XAML-Typ.</span><span class="sxs-lookup"><span data-stu-id="ceb33-116">The input is a XAML type.</span></span> <span data-ttu-id="ceb33-117">Die Beziehung zwischen der Verwendung von XAML-Typ der Eingabe und die Ausgabe CLR <xref:System.Type> ist, die die Ausgabe <xref:System.Type> ist die <xref:System.Xaml.XamlType.UnderlyingType%2A> der Eingabe <xref:System.Xaml.XamlType>, nach der Suche nach den erforderlichen <xref:System.Xaml.XamlType> basierend auf XAML-Schemakontext und die <xref:System.Windows.Markup.IXamlTypeResolver>Dienst, der den Kontext bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ceb33-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="ceb33-118">In .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung von definiert die <xref:System.Windows.Markup.TypeExtension> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ceb33-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="ceb33-119">In bestimmten Frameworks Implementierungen, einige Eigenschaften, die akzeptieren <xref:System.Type> als ein Wert direkt den Namen des Typs akzeptieren kann (den Zeichenfolgenwert des Typs `Name`).</span><span class="sxs-lookup"><span data-stu-id="ceb33-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="ceb33-120">Dieses Verhalten zu implementieren, ist jedoch ein komplexes Szenario.</span><span class="sxs-lookup"><span data-stu-id="ceb33-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="ceb33-121">Beispiele finden Sie im Abschnitt "Hinweise zur WPF-Verwendung" folgt.</span><span class="sxs-lookup"><span data-stu-id="ceb33-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="ceb33-122">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="ceb33-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="ceb33-123">Das Zeichenfolgentoken, das auf die `x:Type`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.TypeExtension.TypeName%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.TypeExtension>-Erweiterungsklasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ceb33-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="ceb33-124">Unter Verwendung von XAML-Standardschemakontext für .NET Framework-XAML-Dienste, die auf CLR-Typen basiert, ist der Wert dieses Attributs die <xref:System.Reflection.MemberInfo.Name%2A> des gewünschten Typs oder die enthält <xref:System.Reflection.MemberInfo.Name%2A> für einen nicht standardmäßigen XAML-Namespace ein Präfix vorangestellt Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="ceb33-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="ceb33-125">Die `x:Type` Markuperweiterung in die Syntax der Object-Element verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ceb33-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="ceb33-126">In diesem Fall geben Sie den Wert der <xref:System.Windows.Markup.TypeExtension.TypeName%2A> Eigenschaft ist erforderlich, um die Erweiterung zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="ceb33-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="ceb33-127">Die `x:Type` Markuperweiterung kann auch als verbose-Attribut verwendet werden; diese Verwendung ist jedoch nicht typisch: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="ceb33-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="ceb33-128">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="ceb33-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="ceb33-129">Standard-XAML-Namespace und Zuordnung</span><span class="sxs-lookup"><span data-stu-id="ceb33-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="ceb33-130">Die Verwendung von XAML-Standardnamespace für WPF-Programmierung enthält die meisten XAML-Typen für typische Verwendung von XAML-Szenarien benötigten; aus diesem Grund können Sie häufig Präfixe vermeiden, wenn XAML-Werte zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="ceb33-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="ceb33-131">Sie müssen möglicherweise ein Präfix zuordnen, wenn Sie einen Typ verweist, aus einer benutzerdefinierten Assembly oder für Typen, die in einer WPF-Assembly vorhanden sein, aber von einem CLR-Namespace, der nicht dem XAML-Standardnamespace zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ceb33-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="ceb33-132">Weitere Informationen über Präfixe, XAML-Namespaces und Zuordnen von CLR-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="ceb33-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="ceb33-133">Geben Sie die Eigenschaften dieser Unterstützung Typename-als-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ceb33-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="ceb33-134">WPF unterstützt Techniken, mit denen die Angabe des Werts einiger Eigenschaften des Typs <xref:System.Type> ohne eine `x:Type` Markuperweiterungsverwendung.</span><span class="sxs-lookup"><span data-stu-id="ceb33-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="ceb33-135">Stattdessen können Sie den Wert als Zeichenfolge angeben, die den Typ benennt.</span><span class="sxs-lookup"><span data-stu-id="ceb33-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="ceb33-136">Beispiele hierfür sind <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> und <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ceb33-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ceb33-137">Unterstützung für dieses Verhalten wird nicht durch den Einsatz von Typkonvertern oder Markuperweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ceb33-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="ceb33-138">Stattdessen ist dies ein Deferral-Verhalten über implementiert <xref:System.Windows.FrameworkElementFactory>.</span><span class="sxs-lookup"><span data-stu-id="ceb33-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="ceb33-139">Silverlight unterstützt eine ähnliche Konvention.</span><span class="sxs-lookup"><span data-stu-id="ceb33-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="ceb33-140">In der Tat Silverlight unterstützt derzeit keine `{x:Type}` in der XAML-sprachunterstützung und akzeptiert keine `{x:Type}` Verwendungen außerhalb von wenigen Fällen, die zur Unterstützung von XAML-WPF-Silverlight Migration vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="ceb33-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="ceb33-141">Aus diesem Grund ist das Verhalten der Typname als Zeichenfolge in alle Silverlight-Eigenschaft "native"-Evaluierung integriert, in dem eine <xref:System.Type> ist der Wert.</span><span class="sxs-lookup"><span data-stu-id="ceb33-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="ceb33-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="ceb33-142">XAML 2009</span></span>  
 <span data-ttu-id="ceb33-143">XAML 2009 bietet zusätzliche Unterstützung für generische Typen und das Funktionsverhalten von ändert `x:TypeArguments` und `x:Type` zur Bereitstellung dieser Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="ceb33-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   <span data-ttu-id="ceb33-144">`x:TypeArguments` und das zugeordnete Objekt-Element für eine generische Objektinstanziierung kann auf andere Elemente als Stamm.</span><span class="sxs-lookup"><span data-stu-id="ceb33-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="ceb33-145">Weitere Informationen finden Sie im Abschnitt "XAML 2009" von [X: TypeArguments-Direktive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span><span class="sxs-lookup"><span data-stu-id="ceb33-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="ceb33-146">XAML 2009 unterstützt eine Syntax zum Angeben von Einschränkung eines generischen Typs in Markup.</span><span class="sxs-lookup"><span data-stu-id="ceb33-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="ceb33-147">Dies kann verwendet werden, durch `x:TypeArguments`, von `x:Type`, oder indem Sie die beiden Funktionen sollten in Kombination.</span><span class="sxs-lookup"><span data-stu-id="ceb33-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="ceb33-148">WPF-XAML-Implementierung, die bei der Verarbeitung von XAML 2009 für Load auch diese Funktion auf die implizite Typkonvertierungsverhalten für bestimmte Frameworkeigenschaften sorgt, mit dem Typ <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="ceb33-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="ceb33-149">In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für loose XAML (, das nicht markupkompiliert ist).</span><span class="sxs-lookup"><span data-stu-id="ceb33-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="ceb33-150">Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="ceb33-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb33-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ceb33-151">See Also</span></span>  
 <xref:System.Windows.Style>  
 [<span data-ttu-id="ceb33-152">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ceb33-152">Styling and Templating</span></span>](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ceb33-153">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="ceb33-153">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="ceb33-154">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="ceb33-154">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
