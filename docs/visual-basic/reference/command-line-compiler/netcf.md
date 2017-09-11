---
title: / netcf | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
dev_langs:
- VB
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 375ec79fe2bf63bc03988ecaad877eb27f43d55b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="netcf"></a><span data-ttu-id="c2848-102">/netcf</span><span class="sxs-lookup"><span data-stu-id="c2848-102">/netcf</span></span>
<span data-ttu-id="c2848-103">Legt für den Compiler [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] als Ziel fest.</span><span class="sxs-lookup"><span data-stu-id="c2848-103">Sets the compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2848-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2848-104">Syntax</span></span>  
  
```  
/netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="c2848-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2848-105">Remarks</span></span>  
 <span data-ttu-id="c2848-106">Die `/netcf` -Option bewirkt, dass die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler Ziel der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] anstelle der vollständigen [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2848-106">The `/netcf` option causes the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] rather than the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="c2848-107">Language-Funktionalität, die nur im vollständigen ist [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c2848-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="c2848-108">Die `/netcf` Option dient mit [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="c2848-108">The `/netcf` option is designed to be used with [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="c2848-109">Die Sprachfeatures deaktiviert `/netcf` sind die Sprachfeatures nicht vorhanden ist, in den Dateien mit `/sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="c2848-109">The language features disabled by `/netcf` are the same language features not present in the files targeted with `/sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2848-110">Die `/netcf` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="c2848-110">The `/netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="c2848-111">Die `/netcf` Option wird festgelegt, wenn ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Device-Projekt geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c2848-111">The `/netcf` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="c2848-112">Die `/netcf` Option ändert die folgenden Sprachfeatures:</span><span class="sxs-lookup"><span data-stu-id="c2848-112">The `/netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="c2848-113">Die [End \<Schlüsselwort > Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) -Schlüsselwort, das Ausführung eines Programms beendet wird, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2848-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="c2848-114">Das folgende Programm wird kompiliert und ausgeführt wird, ohne `/netcf` , aber nicht zum Zeitpunkt der Kompilierung mit `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="c2848-114">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="c2848-115">[!code-vb[VbVbalrCompiler&#34;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c2848-115">[!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span></span>  
  
-   <span data-ttu-id="c2848-116">Späte Bindung, in allen Formularen ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2848-116">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="c2848-117">Kompilierungsfehler werden generiert, wenn erkannten Szenarios für spätes Binden gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c2848-117">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="c2848-118">Das folgende Programm wird kompiliert und ausgeführt wird, ohne `/netcf` , aber nicht zum Zeitpunkt der Kompilierung mit `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="c2848-118">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="c2848-119">[!code-vb[VbVbalrCompiler&#35;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c2848-119">[!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span></span>  
  
-   <span data-ttu-id="c2848-120">Die [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) Modifizierer sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c2848-120">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="c2848-121">Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) -Anweisung wird auch geändert werden, zu `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="c2848-121">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="c2848-122">Der folgende Code zeigt die Auswirkung der `/netcf` auf eine Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="c2848-122">The following code shows the effect of `/netcf` on a compilation.</span></span>  
  
     <span data-ttu-id="c2848-123">[!code-vb[VbVbalrCompiler Nr.&36;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c2848-123">[!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span></span>  
  
-   <span data-ttu-id="c2848-124">Mithilfe von Visual Basic 6.0-Schlüsselwörtern, die aus entfernt wurden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generiert einen anderen Fehler bei der `/netcf` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2848-124">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a different error when `/netcf` is used.</span></span> <span data-ttu-id="c2848-125">Dies wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter:</span><span class="sxs-lookup"><span data-stu-id="c2848-125">This affects the error messages for the following keywords:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="c2848-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2848-126">Example</span></span>  
 <span data-ttu-id="c2848-127">Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] auf Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="c2848-127">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="c2848-128">Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2848-128">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2848-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2848-129">See Also</span></span>  
 <span data-ttu-id="c2848-130">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2848-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c2848-131"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="c2848-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="c2848-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="c2848-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
