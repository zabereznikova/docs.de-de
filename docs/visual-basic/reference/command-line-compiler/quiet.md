---
title: / quiet | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
dev_langs:
- VB
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
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
ms.openlocfilehash: bc21be8982fea52bf25d0bedeec2b78eee1e705f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="quiet"></a><span data-ttu-id="fa198-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="fa198-102">/quiet</span></span>
<span data-ttu-id="fa198-103">Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="fa198-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa198-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa198-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa198-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa198-105">Remarks</span></span>  
 <span data-ttu-id="fa198-106">In der Standardeinstellung ist `/quiet` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="fa198-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="fa198-107">Wenn der Compiler eine Syntax-bezogenen Fehler oder eine Warnung gemeldet wurde, können sie auch die Zeile aus dem Quellcode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fa198-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="fa198-108">Für Anwendungen, die Compilerausgabe zu analysieren, kann es einfacher für den Compiler an, nur der Text der Diagnose Ausgabe sein.</span><span class="sxs-lookup"><span data-stu-id="fa198-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="fa198-109">Im folgenden Beispiel `Module1` gibt einen Fehler aus, die bei der Kompilierung ohne Quellcode enthält `/quiet`.</span><span class="sxs-lookup"><span data-stu-id="fa198-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="fa198-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="fa198-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="fa198-111">Kompilierung mit `/quiet`, gibt der Compiler nur Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fa198-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="fa198-112">Die `/quiet` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="fa198-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa198-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa198-113">Example</span></span>  
 <span data-ttu-id="fa198-114">Der folgende code kompiliert `T2.vb` und Code für syntaxbezogene Compilerdiagnose nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fa198-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa198-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa198-115">See Also</span></span>  
 <span data-ttu-id="fa198-116">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa198-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fa198-117"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="fa198-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
