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
ms.openlocfilehash: 5daff0567c1b1415fe994f6e39b4079cb2ab7346
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053818"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="23ad4-102">x:ClassModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="23ad4-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="23ad4-103">Ändert das XAML-Kompilierungs `x:Class` Verhalten, wenn ebenfalls bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="23ad4-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="23ad4-104">Anstatt eine partielle `class` zu erstellen, die über eine `Public` Zugriffsebene (Standardeinstellung) verfügt, wird `x:Class` der bereitgestellte mit `NotPublic` einer Zugriffsebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="23ad4-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="23ad4-105">Dieses Verhalten wirkt sich auf die Zugriffsebene für die-Klasse in den generierten Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="23ad4-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="23ad4-106">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="23ad4-106">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="23ad4-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="23ad4-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23ad4-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="23ad4-108">*NotPublic*</span></span>|<span data-ttu-id="23ad4-109">Die genaue Zeichenfolge, die an <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> übergeben werden soll, und variiert abhängig von der verwendeten Programmiersprache Code-Behind.</span><span class="sxs-lookup"><span data-stu-id="23ad4-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="23ad4-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="23ad4-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="23ad4-111">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="23ad4-111">Dependencies</span></span>  
 <span data-ttu-id="23ad4-112">[x:Class](x-class-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stamm Element in einer Seite sein.</span><span class="sxs-lookup"><span data-stu-id="23ad4-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="23ad4-113">Weitere Informationen finden [ \[Sie im Abschnitt zu MS-\] XAML 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="23ad4-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23ad4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23ad4-114">Remarks</span></span>  
 <span data-ttu-id="23ad4-115">Der Wert von `x:ClassModifier` in .NET Framework Verwendung der XAML-Dienste hängt von der Programmiersprache ab.</span><span class="sxs-lookup"><span data-stu-id="23ad4-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="23ad4-116">Die zu verwendende Zeichenfolge hängt davon ab, wie <xref:System.CodeDom.Compiler.CodeDomProvider> die jeweilige Sprache implementiert, und die Typkonverter, die <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> zurück <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>gegeben werden, um die Bedeutung für und zu definieren</span><span class="sxs-lookup"><span data-stu-id="23ad4-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="23ad4-117">Für C# <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist`internal`die an zu über gebende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="23ad4-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="23ad4-118">Bei Microsoft Visual Basic .net <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> ist `Friend`die Zeichenfolge, die an übergeben werden soll,.</span><span class="sxs-lookup"><span data-stu-id="23ad4-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="23ad4-119">Für C++/CLI gibt es keine Ziele, die das Kompilieren von XAML unterstützen. Daher ist der zu Übergabe Wert nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="23ad4-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="23ad4-120">Sie können auch ( <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public` in C#, `Public` in Visual Basic) angeben. die Angabe <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> von ist jedoch nur selten durch <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> geführt, da bereits das Standardverhalten ist.</span><span class="sxs-lookup"><span data-stu-id="23ad4-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="23ad4-121">Andere Werte mit äquivalenten Zugriffs ebeneneinschränkungen für den Benutzer `private` Code C#, z. b. `x:ClassModifier` in, sind für nicht relevant, da in XAML keine in XAML <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> unterstützten Klassen Verweise unterstützt werden und der-Modifizierer daher dieselbe Auswirkung hat. .</span><span class="sxs-lookup"><span data-stu-id="23ad4-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="23ad4-122">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="23ad4-122">Security Notes</span></span>  
 <span data-ttu-id="23ad4-123">Die Zugriffsebene, wie Sie `x:ClassModifier` in deklariert wird, unterliegt weiterhin der Interpretation durch bestimmte Frameworks und deren Funktionen.</span><span class="sxs-lookup"><span data-stu-id="23ad4-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="23ad4-124">WPF enthält Funktionen zum Laden und Instanziieren von Typen `x:ClassModifier` , `internal`bei denen ist, wenn auf diese Klasse von einer WPF-Ressource über einen Paket-URI-Verweis verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="23ad4-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="23ad4-125">In diesem Fall und möglicherweise andere, wie Sie von anderen Frameworks implementiert werden, verlassen sich nicht ausschließlich `x:ClassModifier` darauf, dass alle möglichen instanziierungsversuche blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="23ad4-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ad4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23ad4-126">See also</span></span>

- [<span data-ttu-id="23ad4-127">x:Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="23ad4-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="23ad4-128">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="23ad4-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="23ad4-129">x:FieldModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="23ad4-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="23ad4-130">Sicherheit (WPF)</span><span class="sxs-lookup"><span data-stu-id="23ad4-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="23ad4-131">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="23ad4-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
