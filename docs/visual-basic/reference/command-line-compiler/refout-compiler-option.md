---
title: -Refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999467"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="ef8b7-102">-Refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef8b7-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="ef8b7-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="ef8b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef8b7-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="ef8b7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="ef8b7-105">Arguments</span></span>

 <span data-ttu-id="ef8b7-106">`filepath` Der Pfad und Dateiname der Verweisassembly.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-106">`filepath` The path and filename of the reference assembly.</span></span> <span data-ttu-id="ef8b7-107">Es sollte in der Regel in einem Unterordner der primären Assembly sein.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="ef8b7-108">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="ef8b7-109">Alle Ordner im `filepath` muss vorhanden sein; der Compiler nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-109">All folders in `filepath` must exist; the compiler does not create them.</span></span> 

## <a name="remarks"></a><span data-ttu-id="ef8b7-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef8b7-110">Remarks</span></span>

<span data-ttu-id="ef8b7-111">Visual Basic unterstützt die `-refout` ab Version 15.3 zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="ef8b7-112">Verweisassemblys werden Metadaten beschränkten Assemblys, die Metadaten, aber keinen Code zur Implementierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="ef8b7-113">Sie enthalten Informationen von Typ- und Memberinformationen für alles außer anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="ef8b7-114">Ihre Methodentext ersetzt werden, mit einem einzelnen `throw null` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="ef8b7-115">Der Grund für die Verwendung von `throw null` Methodentexten (im Gegensatz zu keinen Texten) ist, damit PEVerify ausführen kann, und übergeben (daher wird die Vollständigkeit der Metadaten überprüft).</span><span class="sxs-lookup"><span data-stu-id="ef8b7-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="ef8b7-116">Verweisassemblys enthalten ein auf Assemblyebene [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="ef8b7-117">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="ef8b7-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="ef8b7-118">Durch dieses Attribut wird Laufzeiten verweigern, beim Laden der Verweisassemblys für die Ausführung (aber immer noch können Sie in einem reflektionsbezogenen Kontext geladen werden).</span><span class="sxs-lookup"><span data-stu-id="ef8b7-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="ef8b7-119">Tools, die Assemblys reflektieren müssen, um sicherzustellen, dass sie die Verweisassemblys nur geladen; Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="ef8b7-120">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="ef8b7-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef8b7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef8b7-121">See Also</span></span>
<span data-ttu-id="ef8b7-122">[-refonly](refonly-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="ef8b7-122">[-refonly](refonly-compiler-option.md) </span></span>  
[<span data-ttu-id="ef8b7-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="ef8b7-123">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="ef8b7-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="ef8b7-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)  

