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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433271"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="dab40-102">x:ClassModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dab40-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="dab40-103">Ändert das XAML-Kompilierungsverhalten, wenn `x:Class` es ebenfalls bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="dab40-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="dab40-104">Anstatt eine `class` Teilebene mit einer `Public` Zugriffsebene (Standardeinstellung) `x:Class` zu erstellen, wird die bereitgestellte Mitschrift mit einer `NotPublic` Zugriffsebene erstellt.</span><span class="sxs-lookup"><span data-stu-id="dab40-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="dab40-105">Dieses Verhalten wirkt sich auf die Zugriffsebene für die Klasse in den generierten Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="dab40-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="dab40-106">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="dab40-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="dab40-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="dab40-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="dab40-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="dab40-108">*NotPublic*</span></span>|<span data-ttu-id="dab40-109">Die genaue Zeichenfolge, <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> die <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> übergeben werden soll, um anzugeben, variiert je nach verwendeter Programmiersprache codebehind.</span><span class="sxs-lookup"><span data-stu-id="dab40-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="dab40-110">Siehe Hinweise.</span><span class="sxs-lookup"><span data-stu-id="dab40-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="dab40-111">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="dab40-111">Dependencies</span></span>

<span data-ttu-id="dab40-112">[x:Class](xclass-directive.md) muss auch für dasselbe Element bereitgestellt werden, und dieses Element muss das Stammelement auf einer Seite sein.</span><span class="sxs-lookup"><span data-stu-id="dab40-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="dab40-113">Weitere Informationen finden Sie unter [ \[\] MS-XAML Abschnitt 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="dab40-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="dab40-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dab40-114">Remarks</span></span>

<span data-ttu-id="dab40-115">Der Wert `x:ClassModifier` der Verwendung von in .NET XAML Services variiert je nach Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="dab40-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="dab40-116">Die zu verwendende Zeichenfolge hängt davon <xref:System.CodeDom.Compiler.CodeDomProvider> ab, wie jede Sprache ihre und <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>die Typkonverter implementiert, die sie zurückgibt, um die Bedeutungen für und zu definieren, und ob die Groß-/Kleinschreibung dieser Sprache berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="dab40-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="dab40-117">Die Zeichenfolge, die übergeben werden <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`soll, ist für C.</span><span class="sxs-lookup"><span data-stu-id="dab40-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="dab40-118">Für Microsoft Visual Basic .NET lautet <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`die Zeichenfolge, die übergeben werden soll, um sie festzulegen, .</span><span class="sxs-lookup"><span data-stu-id="dab40-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="dab40-119">Für C++/CLI sind keine Ziele vorhanden, die das Kompilieren von XAML unterstützen. Daher ist der zu übergebende Wert nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="dab40-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="dab40-120">Sie können <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> auch`public` angeben ( `Public` in C-Code, in Visual Basic); Die Angabe <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> erfolgt jedoch selten, da <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> sie bereits das Standardverhalten ist.</span><span class="sxs-lookup"><span data-stu-id="dab40-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="dab40-121">Andere Werte mit entsprechenden Einschränkungen für Benutzercodezugriffsebene, z. `private` `x:ClassModifier` B. in C,sind nicht relevant, da geschachtelte Klassenverweise in XAML nicht unterstützt werden und der <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Modifikator daher denselben Effekt hat.</span><span class="sxs-lookup"><span data-stu-id="dab40-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="dab40-122">Sicherheitshinweise</span><span class="sxs-lookup"><span data-stu-id="dab40-122">Security Notes</span></span>

<span data-ttu-id="dab40-123">Die in `x:ClassModifier` angegebene Zugangsebene unterliegt nach wie vor der Auslegung durch bestimmte Rahmen und ihre Fähigkeiten.</span><span class="sxs-lookup"><span data-stu-id="dab40-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="dab40-124">WPF enthält Funktionen zum Laden und `x:ClassModifier` Instanziieren von Typen, wobei , `internal`wenn auf diese Klasse von einer WPF-Ressource über einen Pack-URI-Verweis verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dab40-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="dab40-125">Als Folge dieses Falles und möglicherweise andere wie es von anderen `x:ClassModifier` Frameworks implementiert, verlassen Sie sich nicht ausschließlich auf alle möglichen Instanziierungsversuche zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="dab40-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="dab40-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dab40-126">See also</span></span>

- [<span data-ttu-id="dab40-127">x:Class-Direktive</span><span class="sxs-lookup"><span data-stu-id="dab40-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="dab40-128">Code-Behind und XAML in WPF</span><span class="sxs-lookup"><span data-stu-id="dab40-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="dab40-129">x:FieldModifier-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dab40-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="dab40-130">Sicherheit (WPF)</span><span class="sxs-lookup"><span data-stu-id="dab40-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="dab40-131">Aus WPF zu System.Xaml migrierte Typen</span><span class="sxs-lookup"><span data-stu-id="dab40-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
