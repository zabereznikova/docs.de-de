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
ms.openlocfilehash: 3df7e622f97a5a1291736180e3964b1b3deaea2f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005449"
---
# <a name="-netcf"></a><span data-ttu-id="431b9-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="431b9-102">-netcf</span></span>

<span data-ttu-id="431b9-103">Legt den Compiler als Ziel für den .NET Compact Framework fest.</span><span class="sxs-lookup"><span data-stu-id="431b9-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="431b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="431b9-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="431b9-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="431b9-105">Remarks</span></span>

<span data-ttu-id="431b9-106">Die Option "`-netcf`" bewirkt, dass der Visual Basic Compiler die .NET Compact Framework anstelle der vollständigen .NET Framework als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="431b9-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="431b9-107">Sprachfunktionen, die nur in der vollständigen .NET Framework vorhanden sind, sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="431b9-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="431b9-108">Die Option "`-netcf`" ist für die Verwendung mit [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)konzipiert.</span><span class="sxs-lookup"><span data-stu-id="431b9-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="431b9-109">Die von `-netcf` deaktivierten sprach Features sind die gleichen sprach Features, die in den mit `-sdkpath` vorgesehenen Dateien nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="431b9-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="431b9-110">Die Option "`-netcf`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="431b9-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="431b9-111">Die Option "`-netcf`" wird festgelegt, wenn ein Visual Basic Geräte Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="431b9-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="431b9-112">Mit der Option "`-netcf`" werden die folgenden sprach Features geändert:</span><span class="sxs-lookup"><span data-stu-id="431b9-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="431b9-113">Das [End \<-Schlüsselwort > Statement-](../../../visual-basic/language-reference/statements/end-keyword-statement.md) Schlüsselwort, das die Ausführung eines Programms beendet, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="431b9-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="431b9-114">Das folgende Programm wird ohne `-netcf` kompiliert und ausgeführt, schlägt jedoch zur Kompilierzeit mit `-netcf` fehl.</span><span class="sxs-lookup"><span data-stu-id="431b9-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="431b9-115">Spätes Binden ist in allen Formularen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="431b9-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="431b9-116">Kompilierzeitfehler werden generiert, wenn erkannte Szenarien mit späterer Bindung erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="431b9-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="431b9-117">Das folgende Programm wird ohne `-netcf` kompiliert und ausgeführt, schlägt jedoch zur Kompilierzeit mit `-netcf` fehl.</span><span class="sxs-lookup"><span data-stu-id="431b9-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="431b9-118">Die [Auto](../../../visual-basic/language-reference/modifiers/auto.md)-, [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)-und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) -modifiziererer sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="431b9-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="431b9-119">Die Syntax der [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) -Anweisung wird auch in `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]` geändert.</span><span class="sxs-lookup"><span data-stu-id="431b9-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="431b9-120">Der folgende Code zeigt die Auswirkung von `-netcf` auf eine Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="431b9-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="431b9-121">Die Verwendung von Visual Basic 6,0-Schlüsselwörtern, die aus Visual Basic entfernt wurden, generiert bei Verwendung von `-netcf` einen anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="431b9-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="431b9-122">Dies wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter aus:</span><span class="sxs-lookup"><span data-stu-id="431b9-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="431b9-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="431b9-123">Example</span></span>

<span data-ttu-id="431b9-124">Mit dem folgenden Code wird `Myfile.vb` mit dem .NET Compact Framework kompiliert. dabei werden die Versionen von "mscorlib. dll" und "Microsoft. VisualBasic. dll" verwendet, die im Standard Installationsverzeichnis der .NET Compact Framework auf Laufwerk C gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="431b9-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="431b9-125">Normalerweise verwenden Sie die neueste Version der .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="431b9-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="431b9-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="431b9-126">See also</span></span>

- [<span data-ttu-id="431b9-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="431b9-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="431b9-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="431b9-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="431b9-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="431b9-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
