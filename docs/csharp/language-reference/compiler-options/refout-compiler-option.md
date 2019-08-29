---
title: -refout (C# Compileroptionen)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 97cbf540527d0449387b71bb1d97df95b6a4aba4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602506"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="448c2-102">-refout (C# Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="448c2-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="448c2-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="448c2-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="448c2-104">Dies entspricht `metadataPeStream` in der Emit-API.</span><span class="sxs-lookup"><span data-stu-id="448c2-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="448c2-105">Diese Option entspricht der Projekteigenschaft [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.</span><span class="sxs-lookup"><span data-stu-id="448c2-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="448c2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="448c2-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="448c2-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="448c2-107">Arguments</span></span>

 <span data-ttu-id="448c2-108">`filepath`: Der Dateipfad für die Verweisassembly.</span><span class="sxs-lookup"><span data-stu-id="448c2-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="448c2-109">Dieser sollte im Allgemeinen mit der primären Assembly übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="448c2-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="448c2-110">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="448c2-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="448c2-111">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="448c2-111">Remarks</span></span>

<span data-ttu-id="448c2-112">Bei auf Metadaten beschränkten Assemblys werden die Methodentexte durch einen einzigen `throw null`-Text ersetzt, sie enthalten jedoch alle Member außer anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="448c2-112">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="448c2-113">Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).</span><span class="sxs-lookup"><span data-stu-id="448c2-113">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="448c2-114">Verweisassemblys enthalten ein `ReferenceAssembly`-Attribut auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="448c2-114">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="448c2-115">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="448c2-115">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="448c2-116">Durch dieses Attribut wird die Laufzeit das Ausführen von Verweisassemblys verweigert (sie können aber dennoch im reflektionsbezogenen Modus geladen werden).</span><span class="sxs-lookup"><span data-stu-id="448c2-116">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="448c2-117">Tools, die Assemblys reflektieren, müssen sicherstellen, dass Assemblys nur reflektionsbezogen geladen werden. Andernfalls erhalten Sie einen Laufzeitfehler beim Laden von Typen.</span><span class="sxs-lookup"><span data-stu-id="448c2-117">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="448c2-118">Verweisassemblys entfernen außerdem Metadaten (private Member) aus auf Metadaten beschränkten Assemblys:</span><span class="sxs-lookup"><span data-stu-id="448c2-118">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="448c2-119">Eine Verweisassembly verfügt nur über die Verweise, die es in der API-Oberfläche benötigt.</span><span class="sxs-lookup"><span data-stu-id="448c2-119">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="448c2-120">Die echte Assembly kann über zusätzliche Verweise verfügen, die sich auf bestimmte Implementierungen beziehen.</span><span class="sxs-lookup"><span data-stu-id="448c2-120">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="448c2-121">Bei Instanzen verweist die Verweisassembly für `class C { private void M() { dynamic d = 1; ... } }` nicht auf Typen, die für `dynamic` erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="448c2-121">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="448c2-122">Private Funktionsmember (Methoden, Eigenschaften und Ereignisse) werden in den Fällen entfernt, in denen ihre Entfernung sich nicht erkennbar auf die Kompilierung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="448c2-122">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="448c2-123">Wenn keine <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribute vorhanden sind, gehen Sie für interne Funktionsmember genauso vor.</span><span class="sxs-lookup"><span data-stu-id="448c2-123">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="448c2-124">Es werden jedoch alle Typen (einschließlich privater oder geschachtelter Typen) in Verweisassemblys beibehalten.</span><span class="sxs-lookup"><span data-stu-id="448c2-124">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="448c2-125">Alle Attribute (auch interne) werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="448c2-125">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="448c2-126">Alle virtuellen Methoden werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="448c2-126">All virtual methods are kept.</span></span> <span data-ttu-id="448c2-127">Explizite Schnittstellenimplementierungen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="448c2-127">Explicit interface implementations are kept.</span></span> <span data-ttu-id="448c2-128">Explizit implementierte Eigenschaften und Ereignisse werden beibehalten, aber ihre Accessoren sind virtuell (und werden deshalb beibehalten).</span><span class="sxs-lookup"><span data-stu-id="448c2-128">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="448c2-129">Alle Felder einer Struktur werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="448c2-129">All fields of a struct are kept.</span></span> <span data-ttu-id="448c2-130">(Dies ist ein Kandidat für eine Optimierung nach C# 7.1)</span><span class="sxs-lookup"><span data-stu-id="448c2-130">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="448c2-131">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="448c2-131">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="448c2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="448c2-132">See also</span></span>

- [<span data-ttu-id="448c2-133">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="448c2-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="448c2-134">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="448c2-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
