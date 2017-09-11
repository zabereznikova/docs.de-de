---
title: / verbose | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
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
ms.openlocfilehash: 62285a727217aa897a83a9e746588c80a2c519c0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="verbose"></a><span data-ttu-id="e4e95-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="e4e95-102">/verbose</span></span>
<span data-ttu-id="e4e95-103">Veranlasst den Compiler, um ausführliche Status- und Fehlermeldungen zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="e4e95-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4e95-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4e95-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e4e95-105">Arguments</span></span>  
 <span data-ttu-id="e4e95-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e4e95-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e4e95-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="e4e95-107">Optional.</span></span> <span data-ttu-id="e4e95-108">Angeben von `/verbose` entspricht der Angabe `/verbose+`, die bewirkt, dass der Compiler entspricht.</span><span class="sxs-lookup"><span data-stu-id="e4e95-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="e4e95-109">Der Standardwert für diese Option ist `/verbose-`.</span><span class="sxs-lookup"><span data-stu-id="e4e95-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4e95-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4e95-110">Remarks</span></span>  
 <span data-ttu-id="e4e95-111">Die `/verbose` Option zeigt Informationen über die Gesamtzahl der vom Compiler ausgegebenen Fehler meldet, welche Assemblys von einem bestimmten Modul geladen werden und zeigt an, welche Dateien sind gerade kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="e4e95-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4e95-112">Die `/verbose` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="e4e95-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4e95-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4e95-113">Example</span></span>  
 <span data-ttu-id="e4e95-114">Der folgende code kompiliert `In.vb` und weist den Compiler an, um ausführliche Statusinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e4e95-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4e95-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4e95-115">See Also</span></span>  
 <span data-ttu-id="e4e95-116">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4e95-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e4e95-117"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="e4e95-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
