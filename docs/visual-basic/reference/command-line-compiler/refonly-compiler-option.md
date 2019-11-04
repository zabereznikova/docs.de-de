---
title: -Ref only (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775563"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="92827-102">-Ref only (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92827-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="92827-103">Die Option **-rebonly** gibt an, dass die primäre Ausgabe der Kompilierung eine Verweisassembly anstelle einer Implementierungsassembly sein sollte.</span><span class="sxs-lookup"><span data-stu-id="92827-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="92827-104">Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="92827-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="92827-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="92827-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="92827-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92827-106">Remarks</span></span>

<span data-ttu-id="92827-107">Visual Basic unterstützt den `-refonly` Switch ab Version 15,3.</span><span class="sxs-lookup"><span data-stu-id="92827-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="92827-108">Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestanzahl von Metadaten enthält, die zur Darstellung der öffentlichen API-Oberfläche der Bibliothek erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="92827-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="92827-109">Sie enthalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools signifikant sind, aber alle Member-Implementierungen und-Deklarationen von privaten Membern ausschließen, die keine Observable-Auswirkung auf Ihren API-Vertrag haben.</span><span class="sxs-lookup"><span data-stu-id="92827-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="92827-110">Weitere Informationen finden Sie im [Leitfaden zu Verweisassemblys in .net](../../../standard/assembly/reference-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="92827-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="92827-111">Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="92827-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="92827-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92827-112">See also</span></span>

- [<span data-ttu-id="92827-113">/refout</span><span class="sxs-lookup"><span data-stu-id="92827-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="92827-114">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="92827-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="92827-115">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="92827-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
