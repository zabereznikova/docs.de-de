---
title: -refonly (C# Compileroptionen)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: eb62f98c5d548fe3583d3422eb7b6020a82c296a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606484"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="adf81-102">-refonly (C# Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="adf81-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="adf81-103">Die Option **-refonly** gibt an, dass eine Verweisassembly statt einer Implementierungsassembly als primäre Ausgabe ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="adf81-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="adf81-104">Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="adf81-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="adf81-105">Diese Option entspricht der Projekteigenschaft [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.</span><span class="sxs-lookup"><span data-stu-id="adf81-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="adf81-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="adf81-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="adf81-107">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="adf81-107">Remarks</span></span>

<span data-ttu-id="adf81-108">Bei auf Metadaten beschränkten Assemblys werden die Methodentexte durch einen einzigen `throw null`-Text ersetzt, sie enthalten jedoch alle Member außer anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="adf81-108">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="adf81-109">Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).</span><span class="sxs-lookup"><span data-stu-id="adf81-109">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="adf81-110">Verweisassemblys enthalten ein `ReferenceAssembly`-Attribut auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="adf81-110">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="adf81-111">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="adf81-111">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="adf81-112">Durch dieses Attribut wird die Laufzeit das Ausführen von Verweisassemblys verweigert (sie können aber dennoch im reflektionsbezogenen Modus geladen werden).</span><span class="sxs-lookup"><span data-stu-id="adf81-112">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="adf81-113">Tools, die Assemblys reflektieren, müssen sicherstellen, dass Assemblys nur reflektionsbezogen geladen werden. Andernfalls erhalten Sie einen Laufzeitfehler beim Laden von Typen.</span><span class="sxs-lookup"><span data-stu-id="adf81-113">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="adf81-114">Verweisassemblys entfernen außerdem Metadaten (private Member) aus auf Metadaten beschränkten Assemblys:</span><span class="sxs-lookup"><span data-stu-id="adf81-114">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="adf81-115">Eine Verweisassembly verfügt nur über die Verweise, die es in der API-Oberfläche benötigt.</span><span class="sxs-lookup"><span data-stu-id="adf81-115">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="adf81-116">Die echte Assembly kann über zusätzliche Verweise verfügen, die sich auf bestimmte Implementierungen beziehen.</span><span class="sxs-lookup"><span data-stu-id="adf81-116">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="adf81-117">Bei Instanzen verweist die Verweisassembly für `class C { private void M() { dynamic d = 1; ... } }` nicht auf Typen, die für `dynamic` erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="adf81-117">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="adf81-118">Private Funktionsmember (Methoden, Eigenschaften und Ereignisse) werden in den Fällen entfernt, in denen ihre Entfernung sich nicht erkennbar auf die Kompilierung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="adf81-118">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="adf81-119">Wenn keine <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribute vorhanden sind, gehen Sie für interne Funktionsmember genauso vor.</span><span class="sxs-lookup"><span data-stu-id="adf81-119">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="adf81-120">Es werden jedoch alle Typen (einschließlich privater oder geschachtelter Typen) in Verweisassemblys beibehalten.</span><span class="sxs-lookup"><span data-stu-id="adf81-120">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="adf81-121">Alle Attribute (auch interne) werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="adf81-121">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="adf81-122">Alle virtuellen Methoden werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="adf81-122">All virtual methods are kept.</span></span> <span data-ttu-id="adf81-123">Explizite Schnittstellenimplementierungen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="adf81-123">Explicit interface implementations are kept.</span></span> <span data-ttu-id="adf81-124">Explizit implementierte Eigenschaften und Ereignisse werden beibehalten, aber ihre Accessoren sind virtuell (und werden deshalb beibehalten).</span><span class="sxs-lookup"><span data-stu-id="adf81-124">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="adf81-125">Alle Felder einer Struktur werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="adf81-125">All fields of a struct are kept.</span></span> <span data-ttu-id="adf81-126">(Dies ist ein Kandidat für eine Optimierung nach C# 7.1)</span><span class="sxs-lookup"><span data-stu-id="adf81-126">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="adf81-127">Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="adf81-127">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="adf81-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adf81-128">See also</span></span>

- [<span data-ttu-id="adf81-129">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="adf81-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="adf81-130">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="adf81-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
