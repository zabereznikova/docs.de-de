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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837232"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="3a275-102">x:ClassModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a275-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="3a275-103">Ändert das XAML-Kompilierungs Verhalten, wenn `x:Class` ebenfalls bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3a275-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="3a275-104">Anstatt eine partielle `class` zu erstellen, die über eine `Public` Zugriffsebene (Standardeinstellung) verfügt, wird der bereitgestellte `x:Class` mit einer `NotPublic` Zugriffsebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="3a275-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="3a275-105">Dieses Verhalten wirkt sich auf die Zugriffsebene für die-Klasse in den generierten Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="3a275-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3a275-106">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="3a275-106">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3a275-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="3a275-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a275-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="3a275-108">*NotPublic*</span></span>|<span data-ttu-id="3a275-109">Die genaue Zeichenfolge, die an übergeben werden soll, um <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> im Vergleich <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> anzugeben, hängt von der verwendeten Code-Behind-Programmiersprache ab.</span><span class="sxs-lookup"><span data-stu-id="3a275-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="3a275-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="3a275-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="3a275-111">-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="3a275-111">Dependencies</span></span>  
 <span data-ttu-id="3a275-112">[x:Class](x-class-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stamm Element in einer Seite sein.</span><span class="sxs-lookup"><span data-stu-id="3a275-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="3a275-113">Weitere Informationen finden Sie unter [\[MS-XAML\] Abschnitt 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="3a275-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a275-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a275-114">Remarks</span></span>  
 <span data-ttu-id="3a275-115">Der Wert `x:ClassModifier` in .NET Framework der Verwendung von XAML-Diensten hängt von der Programmiersprache ab.</span><span class="sxs-lookup"><span data-stu-id="3a275-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="3a275-116">Die zu verwendende Zeichenfolge hängt davon ab, wie die jeweilige Sprache die <xref:System.CodeDom.Compiler.CodeDomProvider> implementiert, und die Typkonverter, die zurückgegeben werden, um die Bedeutungen für <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> und <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>zu definieren, und ob die Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="3a275-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="3a275-117">Für C#ist die an zu über gebende Zeichenfolge <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`.</span><span class="sxs-lookup"><span data-stu-id="3a275-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="3a275-118">Für Microsoft Visual Basic .net ist die zu über gebende Zeichenfolge <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`.</span><span class="sxs-lookup"><span data-stu-id="3a275-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="3a275-119">Für C++/CLI gibt es keine Ziele, die das Kompilieren von XAML unterstützen. Daher ist der zu Übergabe Wert nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="3a275-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="3a275-120">Sie können auch <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> angeben (`public` in C#, `Public` in Visual Basic); das Angeben von <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> erfolgt jedoch selten, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> bereits das Standardverhalten ist.</span><span class="sxs-lookup"><span data-stu-id="3a275-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="3a275-121">Andere Werte mit äquivalenten Zugriffs ebeneneinschränkungen für den Benutzercode, C#wie z. b. `private` in, sind für `x:ClassModifier` nicht relevant, da in XAML keine in XAML unterstützten Klassen Verweise unterstützt werden und der <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>-Modifizierer daher dieselbe Auswirkung hat.</span><span class="sxs-lookup"><span data-stu-id="3a275-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="3a275-122">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="3a275-122">Security Notes</span></span>  
 <span data-ttu-id="3a275-123">Die in `x:ClassModifier` deklarierte Zugriffsebene unterliegt weiterhin der Interpretation durch bestimmte Frameworks und deren Funktionen.</span><span class="sxs-lookup"><span data-stu-id="3a275-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="3a275-124">WPF enthält Funktionen zum Laden und Instanziieren von Typen, bei denen `x:ClassModifier` `internal`ist, wenn von einer WPF-Ressource über einen Paket-URI-Verweis auf diese Klasse verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3a275-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="3a275-125">In diesem Fall und möglicherweise andere, wie Sie von anderen Frameworks implementiert werden, verlassen sich nicht ausschließlich auf `x:ClassModifier`, um alle möglichen instanziierungsversuche zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="3a275-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a275-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a275-126">See also</span></span>

- [<span data-ttu-id="3a275-127">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a275-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="3a275-128">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="3a275-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="3a275-129">x:FieldModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3a275-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="3a275-130">Sicherheit (WPF)</span><span class="sxs-lookup"><span data-stu-id="3a275-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="3a275-131">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="3a275-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
