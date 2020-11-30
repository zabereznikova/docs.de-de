---
description: -refonly (C# Compileroptionen)
title: -refonly (C# Compileroptionen)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: f9a92462203bedff93a4a711ca8742465b7a561c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "89124746"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="113f0-103">-refonly (C# Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="113f0-103">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="113f0-104">Die Option **-refonly** gibt an, dass eine Verweisassembly statt einer Implementierungsassembly als primäre Ausgabe ausgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="113f0-104">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="113f0-105">Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="113f0-105">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="113f0-106">Diese Option entspricht der Projekteigenschaft [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.</span><span class="sxs-lookup"><span data-stu-id="113f0-106">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="113f0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="113f0-107">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="113f0-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="113f0-108">Remarks</span></span>

<span data-ttu-id="113f0-109">Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestmenge an Metadaten enthalten, die zum Darstellen der öffentlichen API-Oberfläche der Bibliothek erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="113f0-109">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="113f0-110">Sie beinhalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools von Bedeutung sind, schließen aber alle Memberimplementierungen und Deklarationen privater Member aus, die keine beobachtbaren Auswirkungen auf ihren API-Vertrag haben.</span><span class="sxs-lookup"><span data-stu-id="113f0-110">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="113f0-111">Weitere Informationen finden Sie unter [Verweisassemblys](../../../standard/assembly/reference-assemblies.md) im .NET-Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="113f0-111">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="113f0-112">Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="113f0-112">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="113f0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="113f0-113">See also</span></span>

- [<span data-ttu-id="113f0-114">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="113f0-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="113f0-115">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="113f0-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
