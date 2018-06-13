---
title: x:ClassModifier-Anweisung
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 67b53a63dbd6e1377d5684d64ed32b0374c84b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564377"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="f66f8-102">x:ClassModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f66f8-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="f66f8-103">Ändert die XAML-Kompilierungsverhalten beim `x:Class` ebenfalls bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f66f8-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="f66f8-104">Speziell, statt eine partielle `class` , besitzt eine `Public` Zugriffsebene (Standardeinstellung), bereitgestellten `x:Class` wird erstellt, mit einer `NotPublic` Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="f66f8-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="f66f8-105">Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in die generierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="f66f8-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f66f8-106">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="f66f8-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f66f8-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="f66f8-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f66f8-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="f66f8-108">*NotPublic*</span></span>|<span data-ttu-id="f66f8-109">Die genaue Zeichenfolge übergeben, um anzugeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich zu <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> variiert in Abhängigkeit von der Code-Behind-Programmiersprache, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="f66f8-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="f66f8-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="f66f8-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="f66f8-111">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="f66f8-111">Dependencies</span></span>  
 <span data-ttu-id="f66f8-112">[X: Class](../../../docs/framework/xaml-services/x-class-directive.md) muss ebenfalls für dasselbe Element bereitgestellt werden, und dieses Element muss das Stammelement auf einer Seite sein.</span><span class="sxs-lookup"><span data-stu-id="f66f8-112">[x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="f66f8-113">Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="f66f8-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f66f8-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f66f8-114">Remarks</span></span>  
 <span data-ttu-id="f66f8-115">Der Wert des `x:ClassModifier` Verwendung in .NET Framework XAML Services variiert je nach Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="f66f8-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="f66f8-116">Die zu verwendende Zeichenfolge hängt von verschiedenen Sprachen wie implementiert die <xref:System.CodeDom.Compiler.CodeDomProvider> und -Typkonverter, die zurückgegeben wird, um die Bedeutung für definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, und gibt an, ob diese Sprache Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="f66f8-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="f66f8-117">Für c#, die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="f66f8-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="f66f8-118">Für Microsoft Visual Basic .NET, die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `Friend`.</span><span class="sxs-lookup"><span data-stu-id="f66f8-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="f66f8-119">Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], keine Ziele vorhanden sind, die das Kompilieren von XAML unterstützen; daher ist der Wert zur Übergabe nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="f66f8-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="f66f8-120">Sie können auch angeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in c# `Public` in Visual Basic), aber angeben <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> selten geschieht, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist bereits das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="f66f8-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="f66f8-121">Andere Werte durch entsprechende Benutzercode Zugriffsebene Einschränkungen, wie z. B. `private` in c# ist nicht relevant sind für `x:ClassModifier` da geschachtelte Klassenverweise in XAML wird nicht unterstützt werden und daher die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifizierer hat dieselbe Wirkung.</span><span class="sxs-lookup"><span data-stu-id="f66f8-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="f66f8-122">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="f66f8-122">Security Notes</span></span>  
 <span data-ttu-id="f66f8-123">Die Zugriffsebene, die gemäß der Deklaration in `x:ClassModifier` unterliegt Interpretation von bestimmten Frameworks und ihre Funktionen nach wie vor.</span><span class="sxs-lookup"><span data-stu-id="f66f8-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="f66f8-124">WPF enthält Funktionen zum Laden und Instanziieren von Typen, in denen `x:ClassModifier` ist `internal`, sofern dieser Klasse aus einer WPF-Ressource über einen URI-Verweis-Paket verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f66f8-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="f66f8-125">Als Folge dieser Groß-/Kleinschreibung und potenziell andere wie er von anderen Frameworks implementiert, verlassen Sie sich nicht ausschließlich auf `x:ClassModifier` versucht, alle möglichen Instanziierung zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f66f8-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66f8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f66f8-126">See Also</span></span>  
 [<span data-ttu-id="f66f8-127">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f66f8-127">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="f66f8-128">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="f66f8-128">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="f66f8-129">x:FieldModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f66f8-129">x:FieldModifier Directive</span></span>](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [<span data-ttu-id="f66f8-130">Sicherheit (WPF)</span><span class="sxs-lookup"><span data-stu-id="f66f8-130">Security (WPF)</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="f66f8-131">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="f66f8-131">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
