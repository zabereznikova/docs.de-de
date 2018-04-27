---
title: -netcf
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f07fc7988c4329397e464f05d334648e98cb129d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="-netcf"></a><span data-ttu-id="c8bf2-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="c8bf2-102">-netcf</span></span>
<span data-ttu-id="c8bf2-103">Legt für den Compiler [!INCLUDE[Compact](~/includes/compact-md.md)] als Ziel fest.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8bf2-104">Syntax</span></span>  
  
```  
-netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="c8bf2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8bf2-105">Remarks</span></span>  
 <span data-ttu-id="c8bf2-106">Die `-netcf` Option bewirkt, dass die Visual Basic-Compiler zum Ziel der [!INCLUDE[Compact](~/includes/compact-md.md)] anstelle der vollständigen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8bf2-106">The `-netcf` option causes the Visual Basic compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="c8bf2-107">Language-Funktionen, die nur in den vollständigen vorliegt [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="c8bf2-108">Die `-netcf` ist bei Verwendung der Option mit [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="c8bf2-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="c8bf2-109">Die Sprachfunktionen von deaktiviert `-netcf` sind die gleichen Sprachfunktionen, die in den Dateien, die als Ziel für "nicht vorhanden" `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8bf2-110">Die `-netcf` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="c8bf2-111">Die `-netcf` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="c8bf2-112">Die `-netcf` Option ändert die folgenden Sprachfunktionen:</span><span class="sxs-lookup"><span data-stu-id="c8bf2-112">The `-netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="c8bf2-113">Die [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) Schlüsselwort, das Ausführung eines Programms beendet wird, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="c8bf2-114">Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` dagegen ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   <span data-ttu-id="c8bf2-115">Späte Bindung, in allen Formularen: ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="c8bf2-116">Kompilierungsfehler werden generiert, wenn erkannte späte Bindung Szenarien auftreten.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="c8bf2-117">Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` dagegen ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   <span data-ttu-id="c8bf2-118">Die [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) Modifizierer sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="c8bf2-119">Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) -Anweisung wird auch geändert, um `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="c8bf2-120">Der folgende Code zeigt die Auswirkung des `-netcf` auf eine Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-120">The following code shows the effect of `-netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="c8bf2-121">Verwenden von Visual Basic 6.0-Schlüsselwörtern, die aus Visual Basic entfernt wurden, generiert einen anderen Fehler bei der `-netcf` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="c8bf2-122">Dies wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter:</span><span class="sxs-lookup"><span data-stu-id="c8bf2-122">This affects the error messages for the following keywords:</span></span>  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a><span data-ttu-id="c8bf2-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8bf2-123">Example</span></span>  
 <span data-ttu-id="c8bf2-124">Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](~/includes/compact-md.md)], mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" in das Standardverzeichnis für die Installation der gefunden die [!INCLUDE[Compact](~/includes/compact-md.md)] auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="c8bf2-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="c8bf2-125">Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8bf2-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8bf2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8bf2-126">See Also</span></span>  
 [<span data-ttu-id="c8bf2-127">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c8bf2-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c8bf2-128">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c8bf2-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="c8bf2-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="c8bf2-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
