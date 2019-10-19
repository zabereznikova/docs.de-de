---
title: -reout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582870"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="585ef-102">-reout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="585ef-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="585ef-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="585ef-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="585ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="585ef-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="585ef-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="585ef-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="585ef-106">Der Pfad und der Dateiname der Verweisassembly.</span><span class="sxs-lookup"><span data-stu-id="585ef-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="585ef-107">Er sollte sich in der Regel in einem Unterordner der primären Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="585ef-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="585ef-108">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="585ef-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="585ef-109">Alle Ordner in `filepath` müssen vorhanden sein. der Compiler erstellt diese nicht.</span><span class="sxs-lookup"><span data-stu-id="585ef-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="585ef-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="585ef-110">Remarks</span></span>

<span data-ttu-id="585ef-111">Visual Basic unterstützt den `-refout` Switch ab Version 15,3.</span><span class="sxs-lookup"><span data-stu-id="585ef-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="585ef-112">Verweisassemblys sind reine Metadatenassemblys, die Metadaten, aber keinen Implementierungs Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="585ef-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="585ef-113">Sie enthalten Informationen über den Typ und den Member für alles außer anonyme Typen.</span><span class="sxs-lookup"><span data-stu-id="585ef-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="585ef-114">Ihre Methoden Texte werden durch eine einzelne `throw null`-Anweisung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="585ef-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="585ef-115">Der Grund für die Verwendung `throw null` Methoden Texts (im Gegensatz zu keinem Text) ist, dass "Peer verify" ausgeführt und bestanden werden kann (wodurch die Vollständigkeit der Metadaten überprüft wird).</span><span class="sxs-lookup"><span data-stu-id="585ef-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="585ef-116">Verweisassemblys enthalten ein [referenceassembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) -Attribut auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="585ef-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="585ef-117">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="585ef-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="585ef-118">Aufgrund dieses Attributs verweigern Laufzeiten das Laden von Verweisassemblys für die Ausführung (Sie können jedoch dennoch in einen reflektionsbasierten Kontext geladen werden).</span><span class="sxs-lookup"><span data-stu-id="585ef-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="585ef-119">Tools, die Assemblys reflektieren, müssen sicherstellen, dass Sie Verweisassemblys als Reflektion laden. Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException> aus.</span><span class="sxs-lookup"><span data-stu-id="585ef-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="585ef-120">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="585ef-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="585ef-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="585ef-121">See also</span></span>

- [<span data-ttu-id="585ef-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="585ef-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="585ef-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="585ef-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="585ef-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="585ef-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
