---
title: -refout (C# Compileroptionen)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771760"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="4349a-102">-refout (C# Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4349a-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="4349a-103">Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4349a-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="4349a-104">Dies entspricht `metadataPeStream` in der Emit-API.</span><span class="sxs-lookup"><span data-stu-id="4349a-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="4349a-105">Diese Option entspricht der Projekteigenschaft [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4349a-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="4349a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4349a-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="4349a-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="4349a-107">Arguments</span></span>

 <span data-ttu-id="4349a-108">`filepath`: Der Dateipfad für die Verweisassembly.</span><span class="sxs-lookup"><span data-stu-id="4349a-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="4349a-109">Dieser sollte im Allgemeinen mit der primären Assembly übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4349a-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="4349a-110">Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="4349a-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="4349a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4349a-111">Remarks</span></span>

<span data-ttu-id="4349a-112">Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestmenge an Metadaten enthalten, die zum Darstellen der öffentlichen API-Oberfläche der Bibliothek erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4349a-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="4349a-113">Sie beinhalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools von Bedeutung sind, schließen aber alle Memberimplementierungen und Deklarationen privater Member aus, die keine beobachtbaren Auswirkungen auf ihren API-Vertrag haben.</span><span class="sxs-lookup"><span data-stu-id="4349a-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="4349a-114">Weitere Informationen finden Sie unter [Verweisassemblys](../../../standard/assembly/reference-assemblies.md) im .NET-Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="4349a-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="4349a-115">Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="4349a-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="4349a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4349a-116">See also</span></span>

- [<span data-ttu-id="4349a-117">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4349a-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4349a-118">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4349a-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
