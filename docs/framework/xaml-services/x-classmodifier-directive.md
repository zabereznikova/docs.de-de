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
ms.openlocfilehash: cc9e866f859192e1fa13ead24dc44a7b9d286877
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58026783"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="2344b-102">x:ClassModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2344b-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="2344b-103">Ändert die XAML-Kompilierungsverhalten beim `x:Class` wird ebenfalls bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2344b-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="2344b-104">Insbesondere statt einer partiellen `class` , bei dem ein `Public` Zugriffsebene (Standard), der bereitgestellten `x:Class` wird erstellt, mit einer `NotPublic` Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="2344b-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="2344b-105">Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in der generierten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="2344b-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2344b-106">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="2344b-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2344b-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="2344b-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2344b-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="2344b-108">*NotPublic*</span></span>|<span data-ttu-id="2344b-109">Die genaue Zeichenfolge übergeben, um anzugeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich zu <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> variiert in Abhängigkeit von der Code-Behind-Programmiersprache, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="2344b-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="2344b-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="2344b-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="2344b-111">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="2344b-111">Dependencies</span></span>  
 <span data-ttu-id="2344b-112">[X: Class](x-class-directive.md) muss auch angegeben werden, auf das gleiche Element, und dieses Element muss das Stammelement auf einer Seite sein.</span><span class="sxs-lookup"><span data-stu-id="2344b-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="2344b-113">Weitere Informationen finden Sie unter [ \[MS-XAML-\] Abschnitt 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="2344b-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2344b-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2344b-114">Remarks</span></span>  
 <span data-ttu-id="2344b-115">Der Wert des `x:ClassModifier` Nutzung in .NET Framework-XAML-Diensten variiert je nach Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="2344b-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="2344b-116">Wie jede Sprache implementiert, die zu verwendende Zeichenfolge hängt die <xref:System.CodeDom.Compiler.CodeDomProvider> und der Typkonverter wird zurückgegeben, um die Bedeutung für definieren <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, und gibt an, ob die entsprechende Sprache Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="2344b-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="2344b-117">Für C# und die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `internal`.</span><span class="sxs-lookup"><span data-stu-id="2344b-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="2344b-118">Für Microsoft Visual Basic .NET ist die Zeichenfolge übergeben, um zu bestimmen <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `Friend`.</span><span class="sxs-lookup"><span data-stu-id="2344b-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="2344b-119">Für [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], keine Ziele vorhanden sind, die Kompilierung von XAML unterstützen; aus diesem Grund ist der zu übergebende Wert nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="2344b-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="2344b-120">Sie können auch angeben, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C# `Public` in Visual Basic), aber angeben <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> selten geschieht, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ist bereits das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="2344b-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="2344b-121">Andere Werte durch entsprechende Benutzercode Zugriffsebene Einschränkungen, z. B. `private` in C# sind nicht relevant für `x:ClassModifier` da geschachtelte Klassenverweise in XAML, nicht unterstützt werden und somit die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifizierer hat dieselbe Wirkung.</span><span class="sxs-lookup"><span data-stu-id="2344b-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="2344b-122">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="2344b-122">Security Notes</span></span>  
 <span data-ttu-id="2344b-123">Die Zugriffsebene, die gemäß der Deklaration in `x:ClassModifier` interpretiert wird, weiterhin von bestimmten Frameworks und ihre Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2344b-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="2344b-124">WPF enthält Funktionen zum Laden und Instanziieren von Typen, in denen `x:ClassModifier` ist `internal`, wenn die Klasse aus einer WPF-Ressource über einen Paket-URI-Verweis verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2344b-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="2344b-125">Als Folge dieses Falls und potenziell andere wie es von anderen Frameworks implementiert, verlassen Sie sich nicht ausschließlich auf `x:ClassModifier` versucht, alle möglichen Instanziierung zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="2344b-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2344b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2344b-126">See also</span></span>
- [<span data-ttu-id="2344b-127">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2344b-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="2344b-128">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="2344b-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="2344b-129">x:FieldModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2344b-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="2344b-130">Sicherheit (WPF)</span><span class="sxs-lookup"><span data-stu-id="2344b-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="2344b-131">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="2344b-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
