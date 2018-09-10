---
title: -deterministic (C#-Compileroptionen)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f9aca20a3ff65d061c04a21e31db3fb5eab62ba
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274728"
---
# <a name="-deterministic"></a><span data-ttu-id="b0465-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="b0465-102">-deterministic</span></span>

<span data-ttu-id="b0465-103">Bewirkt, dass der Compiler eine Assembly erstellt, deren Byte-für-Byte-Ausgabe über Kompilierungen identisch ist, wenn die Eingaben identisch sind.</span><span class="sxs-lookup"><span data-stu-id="b0465-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="b0465-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0465-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="b0465-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0465-105">Remarks</span></span>

<span data-ttu-id="b0465-106">Standardmäßig ist die Compilerausgabe aus einem vorhandenen Satz von Eingaben eindeutig, da der Compiler einen Zeitstempel und eine GUID hinzufügt, die aus Zufallszahlen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="b0465-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="b0465-107">Verwenden Sie die `-deterministic`-Option zum Erzeugen einer *deterministischen Assembly*. Deren Inhalt im Binärformat muss über Kompilierungen identisch sein, solange die Eingabe identisch ist.</span><span class="sxs-lookup"><span data-stu-id="b0465-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="b0465-108">Der Compiler berücksichtigt die folgenden Eingaben für den Determinismus:</span><span class="sxs-lookup"><span data-stu-id="b0465-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="b0465-109">Die Sequenz der Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="b0465-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="b0465-110">Der Inhalt der rsp-Antwortdatei des Compilers.</span><span class="sxs-lookup"><span data-stu-id="b0465-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="b0465-111">Die genaue Version des verwendeten Compilers und seiner verwiesenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="b0465-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="b0465-112">Der aktuelle Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="b0465-112">The current directory path.</span></span>
- <span data-ttu-id="b0465-113">Die binären Inhalte aller Dateien, die explizit und entweder direkt oder indirekt an den Compiler übergeben werden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="b0465-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
    - <span data-ttu-id="b0465-114">Quelldateien</span><span class="sxs-lookup"><span data-stu-id="b0465-114">Source files</span></span>
    - <span data-ttu-id="b0465-115">Assemblys, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="b0465-115">Referenced assemblies</span></span>
    - <span data-ttu-id="b0465-116">Module, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="b0465-116">Referenced modules</span></span>
    - <span data-ttu-id="b0465-117">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b0465-117">Resources</span></span>
    - <span data-ttu-id="b0465-118">Die Schlüsseldatei mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="b0465-118">The strong name key file</span></span>
    - <span data-ttu-id="b0465-119">@ Antwortdateien</span><span class="sxs-lookup"><span data-stu-id="b0465-119">@ response files</span></span>
    - <span data-ttu-id="b0465-120">Analyzer</span><span class="sxs-lookup"><span data-stu-id="b0465-120">Analyzers</span></span>
    - <span data-ttu-id="b0465-121">RuleSets</span><span class="sxs-lookup"><span data-stu-id="b0465-121">Rulesets</span></span>
    - <span data-ttu-id="b0465-122">Zusätzliche Dateien, die möglicherweise von Analyzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="b0465-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="b0465-123">Die aktuelle Kultur (für die Sprache, in der die Diagnose und die Ausnahmenachrichten erstellt werden).</span><span class="sxs-lookup"><span data-stu-id="b0465-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="b0465-124">Die Standardcodierung (oder die aktuelle Codeseite), wenn die Codierung nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="b0465-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="b0465-125">Das Vorhandensein, Nichtvorhandensein und die Inhalte der Dateien auf den Suchpfaden des Compilers (z.B. von `/lib` oder `/recurse` angegeben).</span><span class="sxs-lookup"><span data-stu-id="b0465-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="b0465-126">Die CLR-Plattform, auf der der Compiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0465-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="b0465-127">Der Wert von `%LIBPATH%`, der das Abhängigkeitsladen des Analyzers beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="b0465-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="b0465-128">Wenn Quellen öffentlich verfügbar sind, kann die deterministische Kompilierung verwendet werden, um festzustellen, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="b0465-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="b0465-129">Sie kann auch in einem fortlaufenden Buildsystem verwendet werden, um zu bestimmen, ob Buildschritte, die von den Änderungen einer Binärdatei abhängig sind, ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b0465-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="b0465-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0465-130">See Also</span></span>  

- [<span data-ttu-id="b0465-131">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="b0465-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="b0465-132">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="b0465-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
