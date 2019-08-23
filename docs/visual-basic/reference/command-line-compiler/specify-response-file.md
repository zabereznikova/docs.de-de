---
title: '@ (Antwortdatei festlegen) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: b84d50334e56305c27c5c0bc54578ba871a28365
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937283"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="971eb-102">@ (Antwortdatei festlegen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="971eb-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="971eb-103">Gibt eine Datei an, die Compileroptionen und Quell Code Dateien enthält, die kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="971eb-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="971eb-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="971eb-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="971eb-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="971eb-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="971eb-106">Required.</span></span> <span data-ttu-id="971eb-107">Eine Datei, die Compileroptionen oder Quell Code Dateien auflistet, die kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="971eb-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="971eb-108">Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="971eb-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="971eb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="971eb-109">Remarks</span></span>  
 <span data-ttu-id="971eb-110">Der Compiler verarbeitet die Compileroptionen und Quell Code Dateien, die in einer Antwortdatei angegeben sind, so, als wären Sie in der Befehlszeile angegeben worden.</span><span class="sxs-lookup"><span data-stu-id="971eb-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="971eb-111">Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Optionen für die Antwortdatei an, wie z. b. die folgenden.</span><span class="sxs-lookup"><span data-stu-id="971eb-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="971eb-112">In einer Antwortdatei können mehrere Compileroptionen und Quell Code Dateien in einer Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="971eb-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="971eb-113">Eine einzelne compileroptionsspezifikation muss in einer Zeile angezeigt werden (darf sich nicht über mehrere Zeilen erstrecken).</span><span class="sxs-lookup"><span data-stu-id="971eb-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="971eb-114">Antwort Dateien können Kommentare enthalten, die mit dem `#` Symbol beginnen.</span><span class="sxs-lookup"><span data-stu-id="971eb-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="971eb-115">Sie können die in der Befehlszeile angegebenen Optionen mit den Optionen kombinieren, die in einer oder mehreren Antwort Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="971eb-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="971eb-116">Der Compiler verarbeitet die Befehlsoptionen, während Sie gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="971eb-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="971eb-117">Daher können Befehlszeilenargumente zuvor aufgelistete Optionen in Antwort Dateien überschreiben.</span><span class="sxs-lookup"><span data-stu-id="971eb-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="971eb-118">Umgekehrt überschreiben Optionen in einer Antwortdatei die zuvor in der Befehlszeile oder in anderen Antwort Dateien aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="971eb-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="971eb-119">Visual Basic stellt die Datei "Vbc. rsp" bereit, die sich im gleichen Verzeichnis wie die Datei "Vbc. exe" befindet.</span><span class="sxs-lookup"><span data-stu-id="971eb-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="971eb-120">Die Datei "Vbc. rsp" ist standardmäßig enthalten `-noconfig` , sofern die Option nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="971eb-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="971eb-121">Weitere Informationen finden Sie unter [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="971eb-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="971eb-122">Die `@` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="971eb-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="971eb-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="971eb-123">Example</span></span>  
 <span data-ttu-id="971eb-124">Die folgenden Zeilen stammen aus einer Beispiel Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="971eb-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="971eb-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="971eb-125">Example</span></span>  
 <span data-ttu-id="971eb-126">Im folgenden Beispiel wird veranschaulicht, wie die `@` -Option mit der Antwortdatei `File1.rsp`mit dem Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="971eb-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="971eb-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="971eb-127">See also</span></span>

- [<span data-ttu-id="971eb-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="971eb-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="971eb-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="971eb-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="971eb-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="971eb-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
