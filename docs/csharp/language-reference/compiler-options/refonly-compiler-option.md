---
title: -refonly (C# Compileroptionen)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: c15308d27b504f22b266e28f6db0caf837ae36c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421210"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="467a7-102">-refonly (C# Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="467a7-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="467a7-103">Die Option **-refonly** gibt an, dass eine Verweisassembly statt einer Implementierungsassembly als primäre Ausgabe ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="467a7-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="467a7-104">Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="467a7-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="467a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="467a7-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="467a7-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="467a7-106">Remarks</span></span>

<span data-ttu-id="467a7-107">Bei auf Metadaten beschränkten Assemblys werden die Methodentexte durch einen einzigen `throw null`-Text ersetzt, sie enthalten jedoch alle Member außer anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="467a7-107">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="467a7-108">Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).</span><span class="sxs-lookup"><span data-stu-id="467a7-108">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="467a7-109">Verweisassemblys enthalten ein `ReferenceAssembly`-Attribut auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="467a7-109">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="467a7-110">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="467a7-110">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="467a7-111">Durch dieses Attribut wird die Laufzeit das Ausführen von Verweisassemblys verweigert (sie können aber dennoch im reflektionsbezogenen Modus geladen werden).</span><span class="sxs-lookup"><span data-stu-id="467a7-111">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="467a7-112">Tools, die Assemblys reflektieren, müssen sicherstellen, dass Assemblys nur reflektionsbezogen geladen werden. Andernfalls erhalten Sie einen Laufzeitfehler beim Laden von Typen.</span><span class="sxs-lookup"><span data-stu-id="467a7-112">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="467a7-113">Verweisassemblys entfernen außerdem Metadaten (private Member) aus auf Metadaten beschränkten Assemblys:</span><span class="sxs-lookup"><span data-stu-id="467a7-113">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="467a7-114">Eine Verweisassembly verfügt nur über die Verweise, die es in der API-Oberfläche benötigt.</span><span class="sxs-lookup"><span data-stu-id="467a7-114">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="467a7-115">Die echte Assembly kann über zusätzliche Verweise verfügen, die sich auf bestimmte Implementierungen beziehen.</span><span class="sxs-lookup"><span data-stu-id="467a7-115">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="467a7-116">Bei Instanzen verweist die Verweisassembly für `class C { private void M() { dynamic d = 1; ... } }` nicht auf Typen, die für `dynamic` erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="467a7-116">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="467a7-117">Private Funktionsmember (Methoden, Eigenschaften und Ereignisse) werden in den Fällen entfernt, in denen ihre Entfernung sich nicht erkennbar auf die Kompilierung auswirkt.</span><span class="sxs-lookup"><span data-stu-id="467a7-117">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="467a7-118">Wenn keine `InternalsVisibleTo`-Attribute vorhanden sind, gehen Sie für interne Funktionsmember genauso vor.</span><span class="sxs-lookup"><span data-stu-id="467a7-118">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="467a7-119">Es werden jedoch alle Typen (einschließlich privater oder geschachtelter Typen) in Verweisassemblys beibehalten.</span><span class="sxs-lookup"><span data-stu-id="467a7-119">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="467a7-120">Alle Attribute (auch interne) werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="467a7-120">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="467a7-121">Alle virtuellen Methoden werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="467a7-121">All virtual methods are kept.</span></span> <span data-ttu-id="467a7-122">Explizite Schnittstellenimplementierungen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="467a7-122">Explicit interface implementations are kept.</span></span> <span data-ttu-id="467a7-123">Explizit implementierte Eigenschaften und Ereignisse werden beibehalten, aber ihre Accessoren sind virtuell (und werden deshalb beibehalten).</span><span class="sxs-lookup"><span data-stu-id="467a7-123">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="467a7-124">Alle Felder einer Struktur werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="467a7-124">All fields of a struct are kept.</span></span> <span data-ttu-id="467a7-125">(Dies ist ein Kandidat für eine Optimierung nach C# 7.1)</span><span class="sxs-lookup"><span data-stu-id="467a7-125">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="467a7-126">Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="467a7-126">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="467a7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="467a7-127">See also</span></span>

- [<span data-ttu-id="467a7-128">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="467a7-128">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="467a7-129">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="467a7-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
