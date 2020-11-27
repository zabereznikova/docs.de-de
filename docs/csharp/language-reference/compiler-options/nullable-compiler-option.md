---
description: -nullable (C#-Compileroptionen)
title: -nullable (C#-Compileroptionen)
author: IEvangelist
ms.author: dapine
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 68857d0cb4d0cd1177506e0b7ce897d2cfc3aa5b
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099223"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="f4b7c-103">-nullable (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="f4b7c-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="f4b7c-104">Mit der Option **-nullable** können Sie den Nullable-Kontext festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-104">The **-nullable** option lets you specify the nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4b7c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4b7c-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="f4b7c-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="f4b7c-106">Arguments</span></span>

<span data-ttu-id="f4b7c-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f4b7c-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="f4b7c-108">Wenn `+` oder **-nullable** festgelegt wird, erlaubt der Compiler Nullable-Kontexte.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-108">Specifying `+`, or **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="f4b7c-109">Wenn `-` angegeben wird, werden Nullable-Kontexte nicht erlaubt. Dies gilt auch, wenn Sie **-nullable** nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-109">Specifying `-`, which is in effect if you don't specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="f4b7c-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="f4b7c-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="f4b7c-111">Mit diesen Argumenten wird die Option für den Nullable-Kontext angegeben.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-111">Specifies the nullable context option.</span></span> <span data-ttu-id="f4b7c-112">Diese funktionieren ähnlich wie die Argumente `+` und `-`, die jeweils zum Zulassen und Verweigern dienen, ermöglichen jedoch eine präzisere Kontrolle über den Nullable-Kontext.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="f4b7c-113">Das `enable`-Argument, das im Grunde genommen mit der Angabe von **-nullable** übereinstimmt, aktiviert den Nullwerte zulassenden Kontext.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="f4b7c-114">Durch Angeben von `disable` werden Nullable-Kontexte nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="f4b7c-115">Wenn das `warnings`-Argument angegeben wird ( **-nullable:warnings**), werden Nullable-Kontexte zugelassen.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="f4b7c-116">Wenn das `annotations`-Argument angegeben wird ( **-nullable:annotations**), werden Nullable-Kontexte zugelassen.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4b7c-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4b7c-117">Remarks</span></span>

<span data-ttu-id="f4b7c-118">Die Ablaufsteuerungsanalyse wird dazu verwendet, die NULL-Zulässigkeit von Variablen in ausführbarem Code abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="f4b7c-119">Die abgeleitete NULL-Zulässigkeit einer Variable ist unabhängig von der deklarierten NULL-Zulässigkeit der Variable.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="f4b7c-120">Methodenaufrufe werden auch analysiert, wenn sie bedingt ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-120">Method calls are analyzed even when they're conditionally omitted.</span></span> <span data-ttu-id="f4b7c-121">Dies gilt beispielsweise für die Methode <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> im Releasemodus.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="f4b7c-122">Das Aufrufen von Methoden, die mit den folgenden Attributen versehen sind, wirken sich auf die Ablaufsteuerungsanalyse aus:</span><span class="sxs-lookup"><span data-stu-id="f4b7c-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="f4b7c-123">Einfache Vorbedingungen: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="f4b7c-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="f4b7c-124">Einfache Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="f4b7c-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="f4b7c-125">Bedingte Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="f4b7c-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="f4b7c-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (z. B. `DoesNotReturnIf(false)` für <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) und <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="f4b7c-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="f4b7c-127">Nachbedingungen für Member: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> und <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="f4b7c-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4b7c-128">Der globale Nullable-Kontext gilt nicht für generierte Codedateien.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-128">The global nullable context does not apply for generated code files.</span></span> <span data-ttu-id="f4b7c-129">Der Nullable-Kontext ist unabhängig von dieser Einstellung für alle als generiert gekennzeichneten Quelldateien *deaktiviert*.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-129">Regardless of this setting, the nullable context is *disabled* for any source file marked as generated.</span></span> <span data-ttu-id="f4b7c-130">Es gibt viel Möglichkeiten, eine Datei als generiert zu markieren:</span><span class="sxs-lookup"><span data-stu-id="f4b7c-130">There are four ways a file is marked as generated:</span></span>
>
> 1. <span data-ttu-id="f4b7c-131">Geben Sie in der EDITORCONFIG-Datei `generated_code = true` in einem Abschnitt an, der für diese Datei gilt.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-131">In the .editorconfig, specify `generated_code = true` in a section that applies to that file.</span></span>
> 1. <span data-ttu-id="f4b7c-132">Fügen Sie `<auto-generated>` oder `<auto-generated/>` ganz oben in der Datei in einem Kommentar ein.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-132">Put `<auto-generated>` or `<auto-generated/>` in a comment at the top of the file.</span></span> <span data-ttu-id="f4b7c-133">Dabei kann es sich um eine beliebige Zeile des Kommentars handeln, jedoch muss es sich beim Kommentarblock um das erste Element in der Datei handeln.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-133">It can be on any line in that comment, but the comment block must be the first element in the file.</span></span>
> 1. <span data-ttu-id="f4b7c-134">Beginnen Sie den Dateinamen mit *TemporaryGeneratedFile_* .</span><span class="sxs-lookup"><span data-stu-id="f4b7c-134">Start the file name with *TemporaryGeneratedFile_*</span></span>
> 1. <span data-ttu-id="f4b7c-135">Enden Sie den Dateinamen mit *.designer.cs*, *.generated.cs*, *.g.cs* oder *.g.i.cs*.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-135">End the file name with *.designer.cs*, *.generated.cs*, *.g.cs*, or *.g.i.cs*.</span></span>
>
> <span data-ttu-id="f4b7c-136">Generatoren können die Präprozessoranweisung [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4b7c-136">Generators can opt-in using the [`#nullable`](../preprocessor-directives/preprocessor-nullable.md) preprocessor directive.</span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="f4b7c-137">Festlegen dieser Compileroption in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="f4b7c-137">To set this compiler option in a project</span></span>

<span data-ttu-id="f4b7c-138">Bearbeiten Sie die *CSPROJ*-Datei, um das `<Nullable>`-Tag in einer `Project/PropertyGroup`-Hierarchie hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f4b7c-138">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="f4b7c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4b7c-139">See also</span></span>

- [<span data-ttu-id="f4b7c-140">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="f4b7c-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f4b7c-141">Präprozessoranweisung `#nullable`</span><span class="sxs-lookup"><span data-stu-id="f4b7c-141">`#nullable` preprocessor directive</span></span>](../preprocessor-directives/preprocessor-nullable.md)
- [<span data-ttu-id="f4b7c-142">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="f4b7c-142">Nullable reference types</span></span>](../../nullable-references.md)
