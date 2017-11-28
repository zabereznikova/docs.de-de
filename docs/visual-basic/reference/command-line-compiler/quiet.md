---
title: /quiet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b816cadb9d805d57a14e9b5df553654dd8167af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="quiet"></a><span data-ttu-id="7fb1b-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="7fb1b-102">/quiet</span></span>
<span data-ttu-id="7fb1b-103">Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fb1b-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="7fb1b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fb1b-105">Remarks</span></span>  
 <span data-ttu-id="7fb1b-106">In der Standardeinstellung ist `/quiet` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="7fb1b-107">Wenn der Compiler ein syntaxbezogene Fehler oder eine Warnung gemeldet wird, können sie auch die Zeile aus Quellcode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="7fb1b-108">Für Anwendungen, die Compilerausgabe zu analysieren, kann es praktischer für den Compiler an, nur den Text der Diagnose ausgegeben sein.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="7fb1b-109">Im folgenden Beispiel `Module1` gibt einen Fehler, der Quellcode bei der Kompilierung ohne enthält `/quiet`.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7fb1b-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7fb1b-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="7fb1b-111">Kompilierte mit `/quiet`, der Compiler gibt nur die folgenden:</span><span class="sxs-lookup"><span data-stu-id="7fb1b-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="7fb1b-112">Die `/quiet` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7fb1b-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fb1b-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7fb1b-113">Example</span></span>  
 <span data-ttu-id="7fb1b-114">Der folgende code kompiliert `T2.vb` und Code für syntaxbezogene Compilerdiagnose nicht angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="7fb1b-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fb1b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fb1b-115">See Also</span></span>  
 [<span data-ttu-id="7fb1b-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="7fb1b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="7fb1b-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="7fb1b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
