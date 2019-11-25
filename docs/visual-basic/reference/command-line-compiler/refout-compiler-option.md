---
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 3649a24a52cc6a448ea7cf4d850915adf02147fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348656"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="71e98-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71e98-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="71e98-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="71e98-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="71e98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71e98-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="71e98-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="71e98-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="71e98-106">The path and filename of the reference assembly.</span><span class="sxs-lookup"><span data-stu-id="71e98-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="71e98-107">It should generally be in a sub-folder of the primary assembly.</span><span class="sxs-lookup"><span data-stu-id="71e98-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="71e98-108">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="71e98-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="71e98-109">All folders in `filepath` must exist; the compiler does not create them.</span><span class="sxs-lookup"><span data-stu-id="71e98-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="71e98-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71e98-110">Remarks</span></span>

<span data-ttu-id="71e98-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span><span class="sxs-lookup"><span data-stu-id="71e98-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="71e98-112">Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestmenge an Metadaten enthalten, die zum Darstellen der öffentlichen API-Oberfläche der Bibliothek erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="71e98-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="71e98-113">Sie beinhalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools von Bedeutung sind, schließen aber alle Memberimplementierungen und Deklarationen privater Member aus, die keine beobachtbaren Auswirkungen auf ihren API-Vertrag haben.</span><span class="sxs-lookup"><span data-stu-id="71e98-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="71e98-114">Weitere Informationen finden Sie unter [Verweisassemblys](../../../standard/assembly/reference-assemblies.md) im .NET-Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="71e98-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="71e98-115">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="71e98-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="71e98-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71e98-116">See also</span></span>

- [<span data-ttu-id="71e98-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="71e98-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="71e98-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="71e98-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="71e98-119">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="71e98-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
