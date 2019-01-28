---
title: -refout (C# Compileroptionen)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 51029c071b3c5bdefe5af798f01238086b8e6d4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589791"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="a0cfa-102">-refout (C# Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a0cfa-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="a0cfa-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="a0cfa-104">Dies entspricht `metadataPeStream` in der Emit-API.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-104">This translates to `metadataPeStream` in the Emit API.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0cfa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0cfa-105">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="a0cfa-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="a0cfa-106">Arguments</span></span>

 <span data-ttu-id="a0cfa-107">`filepath`: Der Dateipfad für die Verweisassembly.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-107">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="a0cfa-108">Dieser sollte im Allgemeinen mit der primären Assembly übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-108">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="a0cfa-109">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0cfa-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0cfa-110">Remarks</span></span>

<span data-ttu-id="a0cfa-111">Bei auf Metadaten beschränkten Assemblys werden die Methodentexte durch einen einzigen `throw null`-Text ersetzt, sie enthalten jedoch alle Member außer anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-111">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="a0cfa-112">Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).</span><span class="sxs-lookup"><span data-stu-id="a0cfa-112">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="a0cfa-113">Verweisassemblys enthalten ein `ReferenceAssembly`-Attribut auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-113">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="a0cfa-114">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="a0cfa-114">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="a0cfa-115">Durch dieses Attribut wird die Laufzeit das Ausführen von Verweisassemblys verweigert (sie können aber dennoch im reflektionsbezogenen Modus geladen werden).</span><span class="sxs-lookup"><span data-stu-id="a0cfa-115">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="a0cfa-116">Tools, die Assemblys reflektieren, müssen sicherstellen, dass Assemblys nur reflektionsbezogen geladen werden. Andernfalls erhalten Sie einen Laufzeitfehler beim Laden von Typen.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-116">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="a0cfa-117">Verweisassemblys entfernen außerdem Metadaten (private Member) aus auf Metadaten beschränkten Assemblys:</span><span class="sxs-lookup"><span data-stu-id="a0cfa-117">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="a0cfa-118">Eine Verweisassembly verfügt nur über die Verweise, die es in der API-Oberfläche benötigt.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-118">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="a0cfa-119">Die echte Assembly kann über zusätzliche Verweise verfügen, die sich auf bestimmte Implementierungen beziehen.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-119">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="a0cfa-120">Bei Instanzen verweist die Verweisassembly für `class C { private void M() { dynamic d = 1; ... } }` nicht auf Typen, die für `dynamic` erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-120">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="a0cfa-121">Private Funktionsmember (Methoden, Eigenschaften und Ereignisse) werden in den Fällen entfernt, in denen ihre Entfernung sich nicht erkennbar auf die Kompilierung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-121">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="a0cfa-122">Wenn keine `InternalsVisibleTo`-Attribute vorhanden sind, gehen Sie für interne Funktionsmember genauso vor.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-122">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="a0cfa-123">Es werden jedoch alle Typen (einschließlich privater oder geschachtelter Typen) in Verweisassemblys beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-123">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="a0cfa-124">Alle Attribute (auch interne) werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-124">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="a0cfa-125">Alle virtuellen Methoden werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-125">All virtual methods are kept.</span></span> <span data-ttu-id="a0cfa-126">Explizite Schnittstellenimplementierungen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-126">Explicit interface implementations are kept.</span></span> <span data-ttu-id="a0cfa-127">Explizit implementierte Eigenschaften und Ereignisse werden beibehalten, aber ihre Accessoren sind virtuell (und werden deshalb beibehalten).</span><span class="sxs-lookup"><span data-stu-id="a0cfa-127">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="a0cfa-128">Alle Felder einer Struktur werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-128">All fields of a struct are kept.</span></span> <span data-ttu-id="a0cfa-129">(Dies ist ein Kandidat für eine Optimierung nach C# 7.1)</span><span class="sxs-lookup"><span data-stu-id="a0cfa-129">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="a0cfa-130">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="a0cfa-130">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0cfa-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0cfa-131">See also</span></span>

- [<span data-ttu-id="a0cfa-132">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="a0cfa-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="a0cfa-133">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="a0cfa-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
