---
title: -nullable (C#-Compileroptionen)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: a68255dba18a022784cd4aaf0027c371893c577b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84449798"
---
# <a name="-nullable-c-compiler-options"></a><span data-ttu-id="753b0-102">-nullable (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="753b0-102">-nullable (C# Compiler Options)</span></span>

<span data-ttu-id="753b0-103">Mit der Option **-nullable** können Sie einen gewünschten Nullable-Kontext festlegen.</span><span class="sxs-lookup"><span data-stu-id="753b0-103">The **-nullable** option lets you specify the desired nullable context.</span></span>

## <a name="syntax"></a><span data-ttu-id="753b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="753b0-104">Syntax</span></span>

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a><span data-ttu-id="753b0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="753b0-105">Arguments</span></span>

<span data-ttu-id="753b0-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="753b0-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="753b0-107">Wenn `+` oder **-nullable** angegeben wird, erlaubt der Compiler Nullable-Kontexte.</span><span class="sxs-lookup"><span data-stu-id="753b0-107">Specifying `+`, or just **-nullable**, causes the compiler to enable nullable context.</span></span> <span data-ttu-id="753b0-108">Wenn `-` angegeben wird, werden Nullable-Kontexte nicht erlaubt. Dies gilt auch, wenn Sie **-nullable** nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="753b0-108">Specifying `-`, which is in effect if you do not specify **-nullable**, disables nullable context.</span></span>

<span data-ttu-id="753b0-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span><span class="sxs-lookup"><span data-stu-id="753b0-109">`enable` &#124; `disable` &#124; `warnings` &#124; `annotations`</span></span>  
<span data-ttu-id="753b0-110">Mit diesen Argumenten wird die Option für den Nullable-Kontext angegeben.</span><span class="sxs-lookup"><span data-stu-id="753b0-110">Specifies the nullable context option.</span></span> <span data-ttu-id="753b0-111">Diese funktionieren ähnlich wie die Argumente `+` und `-`, die jeweils zum Zulassen und Verweigern dienen, ermöglichen jedoch eine präzisere Kontrolle über den Nullable-Kontext.</span><span class="sxs-lookup"><span data-stu-id="753b0-111">Similar to `+` or `-`, to enable and disable, but allows for more granularity of nullable context specificity.</span></span> <span data-ttu-id="753b0-112">Das `enable`-Argument, das im Grunde genommen mit der Angabe von **-nullable** übereinstimmt, aktiviert den Nullwerte zulassenden Kontext.</span><span class="sxs-lookup"><span data-stu-id="753b0-112">The `enable` argument, which is in effect the same as if you specify **-nullable**, enables the nullable context.</span></span> <span data-ttu-id="753b0-113">Durch Angeben von `disable` werden Nullable-Kontexte nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="753b0-113">Specifying `disable` will disable nullable context.</span></span> <span data-ttu-id="753b0-114">Wenn das `warnings`-Argument angegeben wird ( **-nullable:warnings**), werden Nullable-Kontexte zugelassen.</span><span class="sxs-lookup"><span data-stu-id="753b0-114">When providing the `warnings` argument, **-nullable:warnings**, the nullable warning context is enabled.</span></span> <span data-ttu-id="753b0-115">Wenn das `annotations`-Argument angegeben wird ( **-nullable:annotations**), werden Nullable-Kontexte zugelassen.</span><span class="sxs-lookup"><span data-stu-id="753b0-115">When specifying the `annotations` argument, **-nullable:annotations**, the nullable annotation context is enabled.</span></span>

## <a name="remarks"></a><span data-ttu-id="753b0-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="753b0-116">Remarks</span></span>

<span data-ttu-id="753b0-117">Die Ablaufsteuerungsanalyse wird dazu verwendet, die NULL-Zulässigkeit von Variablen in ausführbarem Code abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="753b0-117">Flow analysis is used to infer the nullability of variables within executable code.</span></span> <span data-ttu-id="753b0-118">Die abgeleitete NULL-Zulässigkeit einer Variable ist unabhängig von der deklarierten NULL-Zulässigkeit der Variable.</span><span class="sxs-lookup"><span data-stu-id="753b0-118">The inferred nullability of a variable is independent of the variable's declared nullability.</span></span> <span data-ttu-id="753b0-119">Methodenaufrufe werden auch analysiert, wenn sie bedingt ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="753b0-119">Method calls are analyzed even when they are conditionally omitted.</span></span> <span data-ttu-id="753b0-120">Dies gilt beispielsweise für die Methode <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> im Releasemodus.</span><span class="sxs-lookup"><span data-stu-id="753b0-120">For instance, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in release mode.</span></span>

<span data-ttu-id="753b0-121">Das Aufrufen von Methoden, die mit den folgenden Attributen versehen sind, wirken sich auf die Ablaufsteuerungsanalyse aus:</span><span class="sxs-lookup"><span data-stu-id="753b0-121">Invocation of methods annotated with the following attributes will also affect flow analysis:</span></span>

- <span data-ttu-id="753b0-122">Einfache Vorbedingungen: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span><span class="sxs-lookup"><span data-stu-id="753b0-122">Simple pre-conditions: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute></span></span>
- <span data-ttu-id="753b0-123">Einfache Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span><span class="sxs-lookup"><span data-stu-id="753b0-123">Simple post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullAttribute></span></span>
- <span data-ttu-id="753b0-124">Bedingte Nachbedingungen: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> und <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span><span class="sxs-lookup"><span data-stu-id="753b0-124">Conditional post-conditions: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> and <xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute></span></span>
- <span data-ttu-id="753b0-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (z. B. `DoesNotReturnIf(false)` für <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) und <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span><span class="sxs-lookup"><span data-stu-id="753b0-125"><xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute> (e.g. `DoesNotReturnIf(false)` for <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>) and <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute></span></span>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- <span data-ttu-id="753b0-126">Nachbedingungen für Member: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> und <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span><span class="sxs-lookup"><span data-stu-id="753b0-126">Member post-conditions: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> and <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])></span></span>

### <a name="to-set-this-compiler-option-in-a-project"></a><span data-ttu-id="753b0-127">Festlegen dieser Compileroption in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="753b0-127">To set this compiler option in a project</span></span>

<span data-ttu-id="753b0-128">Bearbeiten Sie die *CSPROJ*-Datei, um das `<Nullable>`-Tag in einer `Project/PropertyGroup`-Hierarchie hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="753b0-128">Edit the *.csproj* to add the `<Nullable>` tag within a `Project/PropertyGroup` hierarchy:</span></span>

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a><span data-ttu-id="753b0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="753b0-129">See also</span></span>

- [<span data-ttu-id="753b0-130">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="753b0-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="753b0-131">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="753b0-131">Nullable reference types</span></span>](../../nullable-references.md)
