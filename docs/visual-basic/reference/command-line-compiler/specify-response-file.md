---
title: '@ (Antwortdatei festlegen)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: c578495bbba0efee79f02da284c7feffb8c12fab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348550"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="50958-102">@ (Antwortdatei festlegen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50958-102">@ (Specify Response File) (Visual Basic)</span></span>

<span data-ttu-id="50958-103">Mit dieser Option wird eine Datei angegeben, die Compileroptionen und zu kompilierende Quellcodedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="50958-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>

## <a name="syntax"></a><span data-ttu-id="50958-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50958-104">Syntax</span></span>

```console
@response_file
```

## <a name="arguments"></a><span data-ttu-id="50958-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="50958-105">Arguments</span></span>

`response_file`  
<span data-ttu-id="50958-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="50958-106">Required.</span></span> <span data-ttu-id="50958-107">Hierbei handelt es sich um eine Datei, die Compileroptionen oder zu kompilierende Quellcodedateien auflistet.</span><span class="sxs-lookup"><span data-stu-id="50958-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="50958-108">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="50958-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>

## <a name="remarks"></a><span data-ttu-id="50958-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50958-109">Remarks</span></span>

<span data-ttu-id="50958-110">Die in einer Antwortdatei angegebenen Compileroptionen und Quellcodedateien werden vom Compiler so verarbeitet, als wären sie in der Befehlszeile angegeben.</span><span class="sxs-lookup"><span data-stu-id="50958-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>

<span data-ttu-id="50958-111">Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Antwortdateioptionen an, z. B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="50958-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>

```console
@file1.rsp @file2.rsp
```

<span data-ttu-id="50958-112">In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="50958-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="50958-113">Eine einzelne Compileroption muss in einer Zeile angegeben werden (und darf nicht mehrere Zeilen umfassen).</span><span class="sxs-lookup"><span data-stu-id="50958-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="50958-114">Antwortdateien können Kommentare aufweisen, die mit einem `#`-Symbol beginnen.</span><span class="sxs-lookup"><span data-stu-id="50958-114">Response files can have comments that begin with the `#` symbol.</span></span>

<span data-ttu-id="50958-115">Sie können in der Befehlszeile angegebene Optionen mit Optionen kombinieren, die in einer oder mehreren Antwortdateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="50958-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="50958-116">Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge, in der sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="50958-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="50958-117">Daher können Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="50958-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="50958-118">Umgekehrt setzen Optionen in einer Antwortdatei zuvor in der Befehlszeile oder in anderen Antwortdateien aufgeführte Optionen außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="50958-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>

<span data-ttu-id="50958-119">Visual Basic stellt die Datei „Vbc.rsp“ bereit, die sich im selben Verzeichnis wie die Datei „Vbc.exe“ befindet.</span><span class="sxs-lookup"><span data-stu-id="50958-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="50958-120">Die Datei „Vbc.rsp“ ist standardmäßig enthalten, es sei denn, die Option `-noconfig` wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="50958-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="50958-121">Weitere Informationen finden Sie unter [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="50958-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>

> [!NOTE]
> <span data-ttu-id="50958-122">Die Option `@` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="50958-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="50958-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50958-123">Example</span></span>

<span data-ttu-id="50958-124">Die folgenden Zeilen stammen aus einer Beispielantwortdatei.</span><span class="sxs-lookup"><span data-stu-id="50958-124">The following lines are from a sample response file.</span></span>

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a><span data-ttu-id="50958-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50958-125">Example</span></span>

<span data-ttu-id="50958-126">Im folgenden Beispiel wird die Verwendung der Option `@` mit der Antwortdatei mit dem Namen `File1.rsp` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50958-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>

```console
vbc @file1.rsp
```

## <a name="see-also"></a><span data-ttu-id="50958-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50958-127">See also</span></span>

- [<span data-ttu-id="50958-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="50958-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="50958-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="50958-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="50958-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="50958-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
