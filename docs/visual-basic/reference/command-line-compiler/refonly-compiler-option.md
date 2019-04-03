---
title: -Refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 4093e98738cf6e41cd450229d82e3672fe9687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819462"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="d2245-102">-Refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2245-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="d2245-103">Die **- Refonly** Option gibt an, dass die primäre Ausgabe von der Kompilierung eine Verweisassembly statt einer implementierungsassembly werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2245-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="d2245-104">Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="d2245-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="d2245-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2245-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="d2245-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2245-106">Remarks</span></span>

<span data-ttu-id="d2245-107">Visual Basic unterstützt die `-refout` ab Version 15.3 zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d2245-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="d2245-108">Verweisassemblys werden Metadaten beschränkten Assemblys, die Metadaten, aber keinen Code zur Implementierung enthalten.</span><span class="sxs-lookup"><span data-stu-id="d2245-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="d2245-109">Sie enthalten Informationen von Typ- und Memberinformationen für alles außer anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="d2245-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="d2245-110">Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).</span><span class="sxs-lookup"><span data-stu-id="d2245-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="d2245-111">Verweisassemblys enthalten ein auf Assemblyebene [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) Attribut.</span><span class="sxs-lookup"><span data-stu-id="d2245-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="d2245-112">Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen).</span><span class="sxs-lookup"><span data-stu-id="d2245-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="d2245-113">Durch dieses Attribut wird Laufzeiten verweigert die Anforderung zum Laden der Verweisassemblys für die Ausführung (aber sie können immer noch in einem reflektionsbezogenen Kontext geladen werden).</span><span class="sxs-lookup"><span data-stu-id="d2245-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="d2245-114">Tools, die Assemblys reflektieren müssen, um sicherzustellen, dass sie die Verweisassemblys nur geladen; Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="d2245-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="d2245-115">Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="d2245-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2245-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2245-116">See also</span></span>

- [<span data-ttu-id="d2245-117">/refout</span><span class="sxs-lookup"><span data-stu-id="d2245-117">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="d2245-118">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d2245-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d2245-119">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d2245-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
