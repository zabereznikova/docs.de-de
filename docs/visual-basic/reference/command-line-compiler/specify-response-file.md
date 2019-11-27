---
title: '@ (Antwortdatei festlegen)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: c578495bbba0efee79f02da284c7feffb8c12fab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348550"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="3cdb7-102">@ (Antwortdatei festlegen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cdb7-102">@ (Specify Response File) (Visual Basic)</span></span>

<span data-ttu-id="3cdb7-103">Gibt eine Datei an, die Compileroptionen und Quell Code Dateien enthält, die kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cdb7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cdb7-104">Syntax</span></span>

```console
@response_file
```

## <a name="arguments"></a><span data-ttu-id="3cdb7-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3cdb7-105">Arguments</span></span>

`response_file`  
<span data-ttu-id="3cdb7-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="3cdb7-106">Required.</span></span> <span data-ttu-id="3cdb7-107">Eine Datei, die Compileroptionen oder Quell Code Dateien auflistet, die kompiliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="3cdb7-108">Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cdb7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cdb7-109">Remarks</span></span>

<span data-ttu-id="3cdb7-110">Der Compiler verarbeitet die Compileroptionen und Quell Code Dateien, die in einer Antwortdatei angegeben sind, so, als wären Sie in der Befehlszeile angegeben worden.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>

<span data-ttu-id="3cdb7-111">Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Optionen für die Antwortdatei an, wie z. b. die folgenden.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>

```console
@file1.rsp @file2.rsp
```

<span data-ttu-id="3cdb7-112">In einer Antwortdatei können mehrere Compileroptionen und Quell Code Dateien in einer Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="3cdb7-113">Eine einzelne compileroptionsspezifikation muss in einer Zeile angezeigt werden (darf sich nicht über mehrere Zeilen erstrecken).</span><span class="sxs-lookup"><span data-stu-id="3cdb7-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="3cdb7-114">Antwort Dateien können Kommentare enthalten, die mit dem `#` Symbol beginnen.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-114">Response files can have comments that begin with the `#` symbol.</span></span>

<span data-ttu-id="3cdb7-115">Sie können die in der Befehlszeile angegebenen Optionen mit den Optionen kombinieren, die in einer oder mehreren Antwort Dateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="3cdb7-116">Der Compiler verarbeitet die Befehlsoptionen, während Sie gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="3cdb7-117">Daher können Befehlszeilenargumente zuvor aufgelistete Optionen in Antwort Dateien überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="3cdb7-118">Umgekehrt überschreiben Optionen in einer Antwortdatei die zuvor in der Befehlszeile oder in anderen Antwort Dateien aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>

<span data-ttu-id="3cdb7-119">Visual Basic stellt die Datei "Vbc. rsp" bereit, die sich im gleichen Verzeichnis wie die Datei "Vbc. exe" befindet.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="3cdb7-120">Die Datei Vbc. rsp ist standardmäßig enthalten, es sei denn, die Option `-noconfig` wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="3cdb7-121">Weitere Informationen finden Sie unter [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="3cdb7-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3cdb7-122">Die `@`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="3cdb7-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cdb7-123">Example</span></span>

<span data-ttu-id="3cdb7-124">Die folgenden Zeilen stammen aus einer Beispiel Antwortdatei.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-124">The following lines are from a sample response file.</span></span>

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a><span data-ttu-id="3cdb7-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3cdb7-125">Example</span></span>

<span data-ttu-id="3cdb7-126">Im folgenden Beispiel wird veranschaulicht, wie die `@`-Option mit der Antwortdatei mit dem Namen `File1.rsp`verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3cdb7-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>

```console
vbc @file1.rsp
```

## <a name="see-also"></a><span data-ttu-id="3cdb7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cdb7-127">See also</span></span>

- [<span data-ttu-id="3cdb7-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="3cdb7-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3cdb7-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="3cdb7-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="3cdb7-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="3cdb7-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
