---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716713"
---
# <a name="-netcf"></a><span data-ttu-id="1f955-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="1f955-102">-netcf</span></span>

<span data-ttu-id="1f955-103">Legt den Compiler als Ziel für den .NET Compact Framework fest.</span><span class="sxs-lookup"><span data-stu-id="1f955-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f955-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f955-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="1f955-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f955-105">Remarks</span></span>

<span data-ttu-id="1f955-106">Die Option `-netcf` bewirkt, dass der Visual Basic Compiler die .NET Compact Framework anstelle der vollständigen .NET Framework als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="1f955-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="1f955-107">Sprachfunktionen, die nur in der vollständigen .NET Framework vorhanden sind, sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f955-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="1f955-108">Die Option `-netcf` ist für die Verwendung mit [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)konzipiert.</span><span class="sxs-lookup"><span data-stu-id="1f955-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="1f955-109">Die sprach Features, die von `-netcf` deaktiviert werden, sind die gleichen sprach Features, die in den Dateien, die `-sdkpath`sind, nicht vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="1f955-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="1f955-110">Die `-netcf`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="1f955-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="1f955-111">Die Option `-netcf` wird festgelegt, wenn ein Visual Basic Geräte Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="1f955-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="1f955-112">Mit der Option `-netcf` werden die folgenden sprach Features geändert:</span><span class="sxs-lookup"><span data-stu-id="1f955-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="1f955-113">Das [End \<-Schlüsselwort > Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) -Schlüsselwort, das die Ausführung eines Programms beendet, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f955-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="1f955-114">Das folgende Programm wird ohne `-netcf` kompiliert und ausgeführt, kann aber zur Kompilierzeit mit `-netcf`nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f955-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="1f955-115">Spätes Binden ist in allen Formularen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f955-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="1f955-116">Kompilierzeitfehler werden generiert, wenn erkannte Szenarien mit späterer Bindung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="1f955-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="1f955-117">Das folgende Programm wird ohne `-netcf` kompiliert und ausgeführt, kann aber zur Kompilierzeit mit `-netcf`nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f955-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="1f955-118">Die [Auto](../../../visual-basic/language-reference/modifiers/auto.md)-, [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)-und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) -modifiziererer sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f955-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="1f955-119">Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) wird ebenfalls in `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`geändert.</span><span class="sxs-lookup"><span data-stu-id="1f955-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="1f955-120">Der folgende Code zeigt die Auswirkungen von `-netcf` auf eine Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="1f955-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="1f955-121">Die Verwendung von Visual Basic 6,0-Schlüsselwörtern, die aus Visual Basic entfernt wurden, generiert bei Verwendung von `-netcf` einen anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="1f955-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="1f955-122">Dies wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter aus:</span><span class="sxs-lookup"><span data-stu-id="1f955-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="1f955-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f955-123">Example</span></span>

<span data-ttu-id="1f955-124">Mit dem folgenden Code wird `Myfile.vb` mit dem .NET Compact Framework kompiliert. dabei werden die Versionen von "mscorlib. dll" und "Microsoft. VisualBasic. dll" verwendet, die im Standard Installationsverzeichnis der .NET Compact Framework auf Laufwerk C gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1f955-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="1f955-125">Normalerweise verwenden Sie die neueste Version der .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="1f955-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="1f955-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f955-126">See also</span></span>

- [<span data-ttu-id="1f955-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="1f955-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1f955-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="1f955-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="1f955-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="1f955-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
