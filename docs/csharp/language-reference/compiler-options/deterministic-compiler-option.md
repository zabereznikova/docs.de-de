---
description: -deterministic (C#-Compileroptionen)
title: -deterministic (C#-Compileroptionen)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
ms.openlocfilehash: d64f4d4b0d4e9b5ed2cc1ee40662dc669fc6660d
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235325"
---
# <a name="-deterministic"></a><span data-ttu-id="6275f-103">-deterministic</span><span class="sxs-lookup"><span data-stu-id="6275f-103">-deterministic</span></span>

<span data-ttu-id="6275f-104">Bewirkt, dass der Compiler eine Assembly erstellt, deren Byte-für-Byte-Ausgabe über Kompilierungen identisch ist, wenn die Eingaben identisch sind.</span><span class="sxs-lookup"><span data-stu-id="6275f-104">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="6275f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6275f-105">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="6275f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6275f-106">Remarks</span></span>

<span data-ttu-id="6275f-107">Standardmäßig ist die Compilerausgabe eindeutig, die aus den Eingaben entsteht, da der Compiler einen Zeitstempel und eine MVID hinzufügt, die aus Zufallszahlen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="6275f-107">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a MVID that is generated from random numbers.</span></span> <span data-ttu-id="6275f-108">Verwenden Sie die `-deterministic`-Option zum Erzeugen einer *deterministischen Assembly*. Deren Inhalt im Binärformat muss über Kompilierungen identisch sein, solange die Eingabe identisch ist.</span><span class="sxs-lookup"><span data-stu-id="6275f-108">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span> <span data-ttu-id="6275f-109">In einem solchen Build werden die Felder für den Zeitstempel und die MVID durch Werte ersetzt, die aus einem Hash aller Kompilierungseingaben abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="6275f-109">In such a build, the timestamp and MVID fields will be replaced with values derived from a hash of all the compilation inputs.</span></span>

<span data-ttu-id="6275f-110">Der Compiler berücksichtigt die folgenden Eingaben für den Determinismus:</span><span class="sxs-lookup"><span data-stu-id="6275f-110">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="6275f-111">Die Sequenz der Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="6275f-111">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="6275f-112">Der Inhalt der rsp-Antwortdatei des Compilers.</span><span class="sxs-lookup"><span data-stu-id="6275f-112">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="6275f-113">Die genaue Version des verwendeten Compilers und seiner verwiesenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="6275f-113">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="6275f-114">Der aktuelle Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="6275f-114">The current directory path.</span></span>
- <span data-ttu-id="6275f-115">Die binären Inhalte aller Dateien, die explizit und entweder direkt oder indirekt an den Compiler übergeben werden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="6275f-115">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="6275f-116">Quelldateien</span><span class="sxs-lookup"><span data-stu-id="6275f-116">Source files</span></span>
  - <span data-ttu-id="6275f-117">Assemblys, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="6275f-117">Referenced assemblies</span></span>
  - <span data-ttu-id="6275f-118">Module, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="6275f-118">Referenced modules</span></span>
  - <span data-ttu-id="6275f-119">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6275f-119">Resources</span></span>
  - <span data-ttu-id="6275f-120">Die Schlüsseldatei mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="6275f-120">The strong name key file</span></span>
  - <span data-ttu-id="6275f-121">@ Antwortdateien</span><span class="sxs-lookup"><span data-stu-id="6275f-121">@ response files</span></span>
  - <span data-ttu-id="6275f-122">Analyzer</span><span class="sxs-lookup"><span data-stu-id="6275f-122">Analyzers</span></span>
  - <span data-ttu-id="6275f-123">RuleSets</span><span class="sxs-lookup"><span data-stu-id="6275f-123">Rulesets</span></span>
  - <span data-ttu-id="6275f-124">Zusätzliche Dateien, die möglicherweise von Analyzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="6275f-124">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="6275f-125">Die aktuelle Kultur (für die Sprache, in der die Diagnose und die Ausnahmenachrichten erstellt werden).</span><span class="sxs-lookup"><span data-stu-id="6275f-125">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="6275f-126">Die Standardcodierung (oder die aktuelle Codeseite), wenn die Codierung nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6275f-126">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="6275f-127">Das Vorhandensein, Nichtvorhandensein und die Inhalte der Dateien auf den Suchpfaden des Compilers (z.B. von `-lib` oder `-recurse` angegeben).</span><span class="sxs-lookup"><span data-stu-id="6275f-127">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="6275f-128">Die CLR-Plattform, auf der der Compiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6275f-128">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="6275f-129">Der Wert von `%LIBPATH%`, der das Abhängigkeitsladen des Analyzers beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="6275f-129">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="6275f-130">Wenn Quellen öffentlich verfügbar sind, kann die deterministische Kompilierung verwendet werden, um festzustellen, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="6275f-130">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="6275f-131">Sie kann auch in einem fortlaufenden Buildsystem verwendet werden, um zu bestimmen, ob Buildschritte, die von den Änderungen einer Binärdatei abhängig sind, ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6275f-131">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6275f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6275f-132">See also</span></span>

- [<span data-ttu-id="6275f-133">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="6275f-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6275f-134">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="6275f-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
