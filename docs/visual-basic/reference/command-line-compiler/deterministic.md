---
title: -deterministisch
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffb1d27f614afc3b07f9d663831fc2071535236f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653207"
---
# <a name="-deterministic"></a><span data-ttu-id="20602-102">-deterministisch</span><span class="sxs-lookup"><span data-stu-id="20602-102">-deterministic</span></span>

<span data-ttu-id="20602-103">Bewirkt, dass der Compiler eine Assembly zu erzeugen, deren Ausgabe Byte für Byte über Kompilierungen für identische Eingaben identisch ist.</span><span class="sxs-lookup"><span data-stu-id="20602-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="20602-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20602-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="20602-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20602-105">Remarks</span></span>

<span data-ttu-id="20602-106">Standardmäßig ist Compilerausgabe aus einem vorhandenen Satz von Eingaben eindeutig, da der Compiler Fügt einen Zeitstempel und eine GUID, die Zufallszahlen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="20602-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="20602-107">Verwenden Sie die `-deterministic` Option zum Erzeugen einer *deterministisch Assembly*, ein, deren Inhalt im Binärformat über Kompilierungen identisch ist, solange die Eingabe identisch ist.</span><span class="sxs-lookup"><span data-stu-id="20602-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="20602-108">Der Compiler berücksichtigt die folgenden Eingaben zum Determinismus:</span><span class="sxs-lookup"><span data-stu-id="20602-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="20602-109">Die Reihenfolge der Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="20602-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="20602-110">Der Inhalt des Compilers rsp-Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="20602-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="20602-111">Die genaue Version des verwendeten Compilers und Assemblys, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="20602-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="20602-112">Der aktuelle Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="20602-112">The current directory path.</span></span>
- <span data-ttu-id="20602-113">Der binäre Inhalt aller Dateien explizit an den Compiler übergeben entweder direkt oder indirekt, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="20602-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="20602-114">Quelldateien</span><span class="sxs-lookup"><span data-stu-id="20602-114">Source files</span></span>
    - <span data-ttu-id="20602-115">Assemblys verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="20602-115">Referenced assemblies</span></span>
    - <span data-ttu-id="20602-116">Module verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="20602-116">Referenced modules</span></span>
    - <span data-ttu-id="20602-117">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="20602-117">Resources</span></span>
    - <span data-ttu-id="20602-118">Die Schlüsseldatei mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="20602-118">The strong name key file</span></span>
    - <span data-ttu-id="20602-119">@ Antwortdateien</span><span class="sxs-lookup"><span data-stu-id="20602-119">@ response files</span></span>
    - <span data-ttu-id="20602-120">Analyzer</span><span class="sxs-lookup"><span data-stu-id="20602-120">Analyzers</span></span>
    - <span data-ttu-id="20602-121">Regelsätze</span><span class="sxs-lookup"><span data-stu-id="20602-121">Rulesets</span></span>
    - <span data-ttu-id="20602-122">Zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden</span><span class="sxs-lookup"><span data-stu-id="20602-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="20602-123">Die aktuelle Kultur (für die Sprache, in der Diagnose, die und die Ausnahme Nachrichten erstellt werden).</span><span class="sxs-lookup"><span data-stu-id="20602-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="20602-124">Die standardcodierung (oder der aktuellen Codepage) Wenn die Codierung nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="20602-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="20602-125">Das Vorhandensein, Nichtvorhandensein und Inhalt der Dateien auf den Compiler Suchpfade (angegeben, z. B. durch `/lib` oder `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="20602-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="20602-126">Die CLR-Plattform, auf der der Compiler ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="20602-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="20602-127">Der Wert des `%LIBPATH%`, kann der Analyzer Abhängigkeit laden beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="20602-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="20602-128">Wenn Quellen öffentlich verfügbar sind, kann deterministisch Kompilierung verwendet werden, zur Feststellung, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="20602-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="20602-129">Sie können auch nützlich sein in einem fortlaufenden Buildsystem zu bestimmen, ob Buildschritte, die abhängig von den Änderungen in einen binären sind ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="20602-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="20602-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20602-130">See Also</span></span>
[<span data-ttu-id="20602-131">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="20602-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
[<span data-ttu-id="20602-132">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="20602-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
