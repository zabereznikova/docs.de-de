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
ms.openlocfilehash: 16fb6b3b63c848ea6c09cc18b0fcc488670f0926
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397474"
---
# <a name="-netcf"></a><span data-ttu-id="f8160-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="f8160-102">-netcf</span></span>

<span data-ttu-id="f8160-103">Legt den Compiler als Ziel für .NET Compact Framework fest.</span><span class="sxs-lookup"><span data-stu-id="f8160-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8160-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8160-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="f8160-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8160-105">Remarks</span></span>

<span data-ttu-id="f8160-106">Die Option `-netcf` bewirkt, dass der Visual Basic-Compiler .NET Compact Framework anstelle des vollständigen .NET Framework anzielt.</span><span class="sxs-lookup"><span data-stu-id="f8160-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="f8160-107">Sprachfeatures, die nur im vollständigen .NET Framework vorhanden sind, sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8160-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="f8160-108">Die `-netcf`-Option ist für die Verwendung mit [-sdkpath](sdkpath.md) konzipiert.</span><span class="sxs-lookup"><span data-stu-id="f8160-108">The `-netcf` option is designed to be used with [-sdkpath](sdkpath.md).</span></span> <span data-ttu-id="f8160-109">Bei den Sprachfeatures, die von `-netcf` deaktiviert werden, handelt es sich um die gleichen Sprachfeatures, die auch in Dateien nicht vorhanden sind, die mit `-sdkpath` angezielt werden.</span><span class="sxs-lookup"><span data-stu-id="f8160-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="f8160-110">Die Option `-netcf` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f8160-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="f8160-111">Die Option `-netcf` wird festgelegt, wenn ein Visual Basic-Geräteprojekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f8160-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="f8160-112">Mit der Option `-netcf` werden die folgenden Sprachfeatures geändert:</span><span class="sxs-lookup"><span data-stu-id="f8160-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="f8160-113">Die [End \<keyword>-Anweisung](../../language-reference/statements/end-keyword-statement.md), die die Ausführung eines Programms beendet, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8160-113">The [End \<keyword> Statement](../../language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="f8160-114">Das folgende Programm kann ohne `-netcf` kompiliert und ausgeführt werden, schlägt aber fehl, wenn `-netcf` zur Kompilierzeit enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f8160-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="f8160-115">Die späte Bindung ist in allen Formularen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8160-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="f8160-116">Wenn späte Bindungen erkannt werden, werden Kompilierzeitfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="f8160-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="f8160-117">Das folgende Programm kann ohne `-netcf` kompiliert und ausgeführt werden, schlägt aber fehl, wenn `-netcf` zur Kompilierzeit enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f8160-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="f8160-118">Die Modifizierer [Auto](../../language-reference/modifiers/auto.md), [ANSI](../../language-reference/modifiers/ansi.md) und [Unicode](../../language-reference/modifiers/unicode.md) werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f8160-118">The [Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md), and [Unicode](../../language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="f8160-119">Die Syntax der [Declare-Anweisung](../../language-reference/statements/declare-statement.md) wird zudem in `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]` geändert.</span><span class="sxs-lookup"><span data-stu-id="f8160-119">The syntax of the [Declare Statement](../../language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="f8160-120">Der folgende Code zeigt die Auswirkungen von `-netcf` auf eine Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="f8160-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="f8160-121">Die Verwendung von Visual Basic 6.0-Schlüsselwörtern, die aus Visual Basic entfernt wurden, generiert bei Verwendung von `-netcf` einen anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="f8160-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="f8160-122">Dieses Verhalten wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter aus:</span><span class="sxs-lookup"><span data-stu-id="f8160-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="f8160-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8160-123">Example</span></span>

<span data-ttu-id="f8160-124">Mit dem folgenden Code wird `Myfile.vb` mit .NET Compact Framework kompiliert. Dabei werden die Versionen von „mscorlib.dll“ und „Microsoft.VisualBasic.dll“ verwendet, die im Standardinstallationsverzeichnis von .NET Compact Framework auf Laufwerk C: gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="f8160-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="f8160-125">Normalerweise verwenden Sie die neueste Version von .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="f8160-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="f8160-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8160-126">See also</span></span>

- [<span data-ttu-id="f8160-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f8160-127">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f8160-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f8160-128">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f8160-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="f8160-129">-sdkpath</span></span>](sdkpath.md)
