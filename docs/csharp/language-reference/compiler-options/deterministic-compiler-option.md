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
ms.openlocfilehash: 9d0bcc2957e5a666c21cdc2ce61e74fc90fe3530
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125825"
---
# <a name="-deterministic"></a><span data-ttu-id="6dbcc-103">-deterministic</span><span class="sxs-lookup"><span data-stu-id="6dbcc-103">-deterministic</span></span>

<span data-ttu-id="6dbcc-104">Bewirkt, dass der Compiler eine Assembly erstellt, deren Byte-für-Byte-Ausgabe über Kompilierungen identisch ist, wenn die Eingaben identisch sind.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-104">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="6dbcc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dbcc-105">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="6dbcc-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6dbcc-106">Remarks</span></span>

<span data-ttu-id="6dbcc-107">Standardmäßig ist die Compilerausgabe aus einem vorhandenen Satz von Eingaben eindeutig, da der Compiler einen Zeitstempel und eine GUID hinzufügt, die aus Zufallszahlen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-107">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="6dbcc-108">Verwenden Sie die `-deterministic`-Option zum Erzeugen einer *deterministischen Assembly*. Deren Inhalt im Binärformat muss über Kompilierungen identisch sein, solange die Eingabe identisch ist.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-108">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="6dbcc-109">Der Compiler berücksichtigt die folgenden Eingaben für den Determinismus:</span><span class="sxs-lookup"><span data-stu-id="6dbcc-109">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="6dbcc-110">Die Sequenz der Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-110">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="6dbcc-111">Der Inhalt der rsp-Antwortdatei des Compilers.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-111">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="6dbcc-112">Die genaue Version des verwendeten Compilers und seiner verwiesenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-112">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="6dbcc-113">Der aktuelle Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-113">The current directory path.</span></span>
- <span data-ttu-id="6dbcc-114">Die binären Inhalte aller Dateien, die explizit und entweder direkt oder indirekt an den Compiler übergeben werden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="6dbcc-114">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="6dbcc-115">Quelldateien</span><span class="sxs-lookup"><span data-stu-id="6dbcc-115">Source files</span></span>
  - <span data-ttu-id="6dbcc-116">Assemblys, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="6dbcc-116">Referenced assemblies</span></span>
  - <span data-ttu-id="6dbcc-117">Module, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="6dbcc-117">Referenced modules</span></span>
  - <span data-ttu-id="6dbcc-118">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6dbcc-118">Resources</span></span>
  - <span data-ttu-id="6dbcc-119">Die Schlüsseldatei mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="6dbcc-119">The strong name key file</span></span>
  - <span data-ttu-id="6dbcc-120">@ Antwortdateien</span><span class="sxs-lookup"><span data-stu-id="6dbcc-120">@ response files</span></span>
  - <span data-ttu-id="6dbcc-121">Analyzer</span><span class="sxs-lookup"><span data-stu-id="6dbcc-121">Analyzers</span></span>
  - <span data-ttu-id="6dbcc-122">RuleSets</span><span class="sxs-lookup"><span data-stu-id="6dbcc-122">Rulesets</span></span>
  - <span data-ttu-id="6dbcc-123">Zusätzliche Dateien, die möglicherweise von Analyzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="6dbcc-123">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="6dbcc-124">Die aktuelle Kultur (für die Sprache, in der die Diagnose und die Ausnahmenachrichten erstellt werden).</span><span class="sxs-lookup"><span data-stu-id="6dbcc-124">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="6dbcc-125">Die Standardcodierung (oder die aktuelle Codeseite), wenn die Codierung nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-125">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="6dbcc-126">Das Vorhandensein, Nichtvorhandensein und die Inhalte der Dateien auf den Suchpfaden des Compilers (z.B. von `-lib` oder `-recurse` angegeben).</span><span class="sxs-lookup"><span data-stu-id="6dbcc-126">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="6dbcc-127">Die CLR-Plattform, auf der der Compiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-127">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="6dbcc-128">Der Wert von `%LIBPATH%`, der das Abhängigkeitsladen des Analyzers beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-128">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="6dbcc-129">Wenn Quellen öffentlich verfügbar sind, kann die deterministische Kompilierung verwendet werden, um festzustellen, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-129">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="6dbcc-130">Sie kann auch in einem fortlaufenden Buildsystem verwendet werden, um zu bestimmen, ob Buildschritte, die von den Änderungen einer Binärdatei abhängig sind, ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6dbcc-130">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dbcc-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dbcc-131">See also</span></span>

- [<span data-ttu-id="6dbcc-132">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="6dbcc-132">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6dbcc-133">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="6dbcc-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
