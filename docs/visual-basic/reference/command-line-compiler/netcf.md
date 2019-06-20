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
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268283"
---
# <a name="-netcf"></a><span data-ttu-id="6c1a1-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="6c1a1-102">-netcf</span></span>

<span data-ttu-id="6c1a1-103">Legt fest, den Compiler an, die .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c1a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c1a1-104">Syntax</span></span>

```
-netcf
```

## <a name="remarks"></a><span data-ttu-id="6c1a1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c1a1-105">Remarks</span></span>

<span data-ttu-id="6c1a1-106">Die `-netcf` Option bewirkt, dass Visual Basic-Compiler auf .NET Compact Framework statt des vollständigen .NET Framework abzielt.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="6c1a1-107">Language-Funktionen, die nur im vollständigen .NET Framework ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="6c1a1-108">Die `-netcf` Option dient für zu verwendenden [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="6c1a1-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="6c1a1-109">Die Sprachfunktionen, die deaktiviert `-netcf` sind die gleichen Sprachfunktionen, die nicht vorhanden ist, in den Dateien, die angesprochenen `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="6c1a1-110">Die `-netcf` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="6c1a1-111">Die `-netcf` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="6c1a1-112">Die `-netcf` Option ändert die folgenden Sprachfunktionen:</span><span class="sxs-lookup"><span data-stu-id="6c1a1-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="6c1a1-113">Die [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) -Schlüsselwort, das Ausführung eines Programms beendet wird, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="6c1a1-114">Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` jedoch ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="6c1a1-115">Späte Bindung, in allen Formularen: ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="6c1a1-116">Kompilierungsfehler werden generiert, wenn bekannte Szenarios für spätes Binden gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="6c1a1-117">Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` jedoch ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="6c1a1-118">Die [automatisch](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) Modifizierer sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="6c1a1-119">Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) Anweisung hat sich ebenfalls geändert `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="6c1a1-120">Der folgende Code zeigt die Auswirkungen der `-netcf` auf eine Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="6c1a1-121">Verwenden von Visual Basic 6.0-Schlüsselwörtern, die von Visual Basic entfernt wurden, generiert einen anderen Fehler bei der `-netcf` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="6c1a1-122">Dies wirkt sich auf, die Fehlermeldungen für die folgenden Schlüsselwörter:</span><span class="sxs-lookup"><span data-stu-id="6c1a1-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="6c1a1-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c1a1-123">Example</span></span>

<span data-ttu-id="6c1a1-124">Der folgende code kompiliert `Myfile.vb` mit .NET Compact Framework, mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von .NET Compact Framework auf dem Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="6c1a1-125">In der Regel verwenden Sie die neueste Version von .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="6c1a1-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="6c1a1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c1a1-126">See also</span></span>

- [<span data-ttu-id="6c1a1-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6c1a1-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6c1a1-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6c1a1-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6c1a1-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="6c1a1-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
