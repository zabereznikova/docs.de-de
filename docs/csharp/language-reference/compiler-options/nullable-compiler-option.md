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
ms.openlocfilehash: f9c6c204d2563865f741c6ddb4644eb56f956c12
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125045"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="bd453-103">-nullable (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="bd453-103">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="bd453-104">Mit der Option **-nullable** können Sie einen gewünschten Nullable-Kontext festlegen.</span><span class="sxs-lookup"><span data-stu-id="bd453-104">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd453-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd453-105">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="bd453-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="bd453-106">Arguments</span></span>

<span data-ttu-id="bd453-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bd453-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="bd453-108">Wenn `+` oder **-nullable** angegeben wird, erlaubt der Compiler Nullable-Kontexte.</span><span class="sxs-lookup"><span data-stu-id="bd453-108">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="bd453-109">Wenn `-` angegeben wird, werden Nullable-Kontexte nicht erlaubt. Dies gilt auch, wenn Sie **-nullable** nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="bd453-109">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="bd453-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="bd453-110">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="bd453-111">Mit diesen Argumenten wird die Option für den Nullable-Kontext angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd453-111">Specifies the nullable context option.</span></span> <span data-ttu-id="bd453-112">Diese funktionieren ähnlich wie die Argumente `+` und `-`, die jeweils zum Zulassen und Verweigern dienen, ermöglichen jedoch eine präzisere Kontrolle über den Nullable-Kontext.</span><span class="sxs-lookup"><span data-stu-id="bd453-112">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="bd453-113">Das `enable`-Argument, das im Grunde genommen mit der Angabe von **-nullable** übereinstimmt, aktiviert den Nullwerte zulassenden Kontext.</span><span class="sxs-lookup"><span data-stu-id="bd453-113">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="bd453-114">Durch Angeben von `disable` werden Nullable-Kontexte nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="bd453-114">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="bd453-115">Wenn das `warnings`-Argument angegeben wird ( **-nullable:warnings**), werden Nullable-Kontexte zugelassen.</span><span class="sxs-lookup"><span data-stu-id="bd453-115">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="bd453-116">Wenn das `annotations`-Argument angegeben wird ( **-nullable:annotations**), werden Nullable-Kontexte zugelassen.</span><span class="sxs-lookup"><span data-stu-id="bd453-116">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd453-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd453-117">Remarks</span></span>

<span data-ttu-id="bd453-118">Die Ablaufsteuerungsanalyse wird dazu verwendet, die NULL-Zulässigkeit von Variablen in ausführbarem Code abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="bd453-118">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="bd453-119">Die abgeleitete NULL-Zulässigkeit einer Variable ist unabhängig von der deklarierten NULL-Zulässigkeit der Variable.</span><span class="sxs-lookup"><span data-stu-id="bd453-119">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="bd453-120">Methodenaufrufe werden auch analysiert, wenn sie bedingt ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="bd453-120">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="bd453-121">Dies gilt beispielsweise für die Methode <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> im Releasemodus.</span><span class="sxs-lookup"><span data-stu-id="bd453-121">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="bd453-122">Das Aufrufen von Methoden, die mit den folgenden Attributen versehen sind, wirken sich auf die Ablaufsteuerungsanalyse aus:</span><span class="sxs-lookup"><span data-stu-id="bd453-122">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="bd453-123">Einfache Vorbedingungen: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="bd453-123">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="bd453-124">Einfache Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="bd453-124">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="bd453-125">Bedingte Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="bd453-125">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="bd453-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (z. B. `DoesNotReturnIf(false)` für <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) und <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="bd453-126"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (for example, `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="bd453-127">Nachbedingungen für Member: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> und <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="bd453-127">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="bd453-128">Festlegen dieser Compileroption in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="bd453-128">To set this compiler option in a project</span></span>

<span data-ttu-id="bd453-129">Bearbeiten Sie die *CSPROJ*-Datei, um das `<Nullable>`-Tag in einer `Project/PropertyGroup`-Hierarchie hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="bd453-129">Edit the *.csproj* file to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="bd453-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd453-130">See also</span></span>

- [<span data-ttu-id="bd453-131">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="bd453-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="bd453-132">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="bd453-132">Nullable reference types</span></span>](../../nullable-references.md)
