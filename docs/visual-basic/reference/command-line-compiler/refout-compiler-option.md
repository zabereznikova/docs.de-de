---
title: -reout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775551"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="24cb5-102">-reout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24cb5-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="24cb5-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="24cb5-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="24cb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24cb5-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="24cb5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="24cb5-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="24cb5-106">Der Pfad und der Dateiname der Verweisassembly.</span><span class="sxs-lookup"><span data-stu-id="24cb5-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="24cb5-107">Er sollte sich in der Regel in einem Unterordner der primären Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="24cb5-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="24cb5-108">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="24cb5-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="24cb5-109">Alle Ordner in `filepath` müssen vorhanden sein. der Compiler erstellt diese nicht.</span><span class="sxs-lookup"><span data-stu-id="24cb5-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="24cb5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24cb5-110">Remarks</span></span>

<span data-ttu-id="24cb5-111">Visual Basic unterstützt den `-refout` Switch ab Version 15,3.</span><span class="sxs-lookup"><span data-stu-id="24cb5-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="24cb5-112">Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestanzahl von Metadaten enthält, die zur Darstellung der öffentlichen API-Oberfläche der Bibliothek erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="24cb5-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="24cb5-113">Sie enthalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools signifikant sind, aber alle Member-Implementierungen und-Deklarationen von privaten Membern ausschließen, die keine Observable-Auswirkung auf Ihren API-Vertrag haben.</span><span class="sxs-lookup"><span data-stu-id="24cb5-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="24cb5-114">Weitere Informationen finden Sie im [Leitfaden zu Verweisassemblys in .net](../../../standard/assembly/reference-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="24cb5-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="24cb5-115">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="24cb5-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="24cb5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24cb5-116">See also</span></span>

- [<span data-ttu-id="24cb5-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="24cb5-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="24cb5-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="24cb5-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="24cb5-119">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="24cb5-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
