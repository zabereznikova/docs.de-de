---
title: '@ (Antwortdatei festlegen) (Visual Basic)'
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af66000208dee0896792892a52dc6acdf5cb1e37
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="1c9a1-102">@ (Antwortdatei festlegen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c9a1-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="1c9a1-103">Gibt eine Datei mit Compileroptionen und Quellcodedateien zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c9a1-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c9a1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1c9a1-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="1c9a1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-106">Required.</span></span> <span data-ttu-id="1c9a1-107">Eine Datei, die Compileroptionen und Quellcodedateien kompilieren auflistet.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="1c9a1-108">Setzen Sie den Dateinamen in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c9a1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c9a1-109">Remarks</span></span>  
 <span data-ttu-id="1c9a1-110">Der Compiler verarbeitet die Compileroptionen und Quellcodedateien in einer Antwortdatei angegeben werden, als ob sie in der Befehlszeile angegeben gewesen.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="1c9a1-111">Um mehr als eine Antwortdatei in einer Kompilierung anzugeben, geben Sie mehrere Antwortdatei Optionen, wie z. B. die folgenden.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="1c9a1-112">In einer Antwort können mehrere Compileroptionen und Quellcodedateien in einer Zeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="1c9a1-113">Eine einzelne Compileroption-Spezifikation muss in einer Zeile angezeigt werden (kann nicht mehrere Zeilen umfassen).</span><span class="sxs-lookup"><span data-stu-id="1c9a1-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="1c9a1-114">Antwortdateien können Kommentare, die mit der `#` Symbol.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="1c9a1-115">Sie können in eine oder mehrere Antwortdateien angegebenen Optionen in der Befehlszeile angegebene Optionen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="1c9a1-116">Der Compiler verarbeitet die Befehlsoptionen an, sobald diese auftreten.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="1c9a1-117">Aus diesem Grund können die Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien überschreiben.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="1c9a1-118">Im Gegensatz dazu überschreiben Optionen in einer Antwortdatei in der Befehlszeile oder in anderen Antwortdateien zuvor aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="1c9a1-119">Visual Basic bietet die Datei "vbc.rsp", die sich im selben Verzeichnis wie die Datei Vbc.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="1c9a1-120">Die Datei "vbc.rsp" ist standardmäßig enthalten, es sei denn, die `-noconfig` Option verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="1c9a1-121">Weitere Informationen finden Sie unter [- Noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="1c9a1-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c9a1-122">Die `@` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c9a1-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c9a1-123">Example</span></span>  
 <span data-ttu-id="1c9a1-124">Die folgenden Zeilen werden aus einer Beispiel-Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="1c9a1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c9a1-125">Example</span></span>  
 <span data-ttu-id="1c9a1-126">Im folgenden Beispiel wird veranschaulicht, wie die `@` Option mit der Antwortdatei, die mit dem Namen `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="1c9a1-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c9a1-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c9a1-127">See Also</span></span>  
 [<span data-ttu-id="1c9a1-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="1c9a1-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1c9a1-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="1c9a1-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="1c9a1-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="1c9a1-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
