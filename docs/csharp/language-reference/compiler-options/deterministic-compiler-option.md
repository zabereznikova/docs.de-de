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
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46528995"
---
# <a name="-deterministic"></a><span data-ttu-id="854b3-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="854b3-102">-deterministic</span></span>

<span data-ttu-id="854b3-103">Bewirkt, dass der Compiler eine Assembly erstellt, deren Byte-für-Byte-Ausgabe über Kompilierungen identisch ist, wenn die Eingaben identisch sind.</span><span class="sxs-lookup"><span data-stu-id="854b3-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="854b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="854b3-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="854b3-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="854b3-105">Remarks</span></span>

<span data-ttu-id="854b3-106">Standardmäßig ist die Compilerausgabe aus einem vorhandenen Satz von Eingaben eindeutig, da der Compiler einen Zeitstempel und eine GUID hinzufügt, die aus Zufallszahlen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="854b3-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="854b3-107">Verwenden Sie die `-deterministic`-Option zum Erzeugen einer *deterministischen Assembly*. Deren Inhalt im Binärformat muss über Kompilierungen identisch sein, solange die Eingabe identisch ist.</span><span class="sxs-lookup"><span data-stu-id="854b3-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="854b3-108">Der Compiler berücksichtigt die folgenden Eingaben für den Determinismus:</span><span class="sxs-lookup"><span data-stu-id="854b3-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="854b3-109">Die Sequenz der Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="854b3-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="854b3-110">Der Inhalt der rsp-Antwortdatei des Compilers.</span><span class="sxs-lookup"><span data-stu-id="854b3-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="854b3-111">Die genaue Version des verwendeten Compilers und seiner verwiesenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="854b3-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="854b3-112">Der aktuelle Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="854b3-112">The current directory path.</span></span>
- <span data-ttu-id="854b3-113">Die binären Inhalte aller Dateien, die explizit und entweder direkt oder indirekt an den Compiler übergeben werden, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="854b3-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
    - <span data-ttu-id="854b3-114">Quelldateien</span><span class="sxs-lookup"><span data-stu-id="854b3-114">Source files</span></span>
    - <span data-ttu-id="854b3-115">Assemblys, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="854b3-115">Referenced assemblies</span></span>
    - <span data-ttu-id="854b3-116">Module, auf die verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="854b3-116">Referenced modules</span></span>
    - <span data-ttu-id="854b3-117">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="854b3-117">Resources</span></span>
    - <span data-ttu-id="854b3-118">Die Schlüsseldatei mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="854b3-118">The strong name key file</span></span>
    - <span data-ttu-id="854b3-119">@ Antwortdateien</span><span class="sxs-lookup"><span data-stu-id="854b3-119">@ response files</span></span>
    - <span data-ttu-id="854b3-120">Analyzer</span><span class="sxs-lookup"><span data-stu-id="854b3-120">Analyzers</span></span>
    - <span data-ttu-id="854b3-121">RuleSets</span><span class="sxs-lookup"><span data-stu-id="854b3-121">Rulesets</span></span>
    - <span data-ttu-id="854b3-122">Zusätzliche Dateien, die möglicherweise von Analyzern verwendet werden</span><span class="sxs-lookup"><span data-stu-id="854b3-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="854b3-123">Die aktuelle Kultur (für die Sprache, in der die Diagnose und die Ausnahmenachrichten erstellt werden).</span><span class="sxs-lookup"><span data-stu-id="854b3-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="854b3-124">Die Standardcodierung (oder die aktuelle Codeseite), wenn die Codierung nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="854b3-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="854b3-125">Das Vorhandensein, Nichtvorhandensein und die Inhalte der Dateien auf den Suchpfaden des Compilers (z.B. von `/lib` oder `/recurse` angegeben).</span><span class="sxs-lookup"><span data-stu-id="854b3-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="854b3-126">Die CLR-Plattform, auf der der Compiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="854b3-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="854b3-127">Der Wert von `%LIBPATH%`, der das Abhängigkeitsladen des Analyzers beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="854b3-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="854b3-128">Wenn Quellen öffentlich verfügbar sind, kann die deterministische Kompilierung verwendet werden, um festzustellen, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="854b3-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="854b3-129">Sie kann auch in einem fortlaufenden Buildsystem verwendet werden, um zu bestimmen, ob Buildschritte, die von den Änderungen einer Binärdatei abhängig sind, ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="854b3-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="854b3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="854b3-130">See Also</span></span>  

- [<span data-ttu-id="854b3-131">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="854b3-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="854b3-132">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="854b3-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
