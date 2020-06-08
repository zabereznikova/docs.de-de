---
title: '@ (Antwortdatei festlegen)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 91cf1b5a55d16ab47a83fbd259dd1d83d8e9c31a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403095"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="8f2f1-102">@ (Antwortdatei festlegen) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f2f1-102">@ (Specify Response File) (Visual Basic)</span></span>

<span data-ttu-id="8f2f1-103">Mit dieser Option wird eine Datei angegeben, die Compileroptionen und zu kompilierende Quellcodedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f2f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f2f1-104">Syntax</span></span>

```console
@response_file
```

## <a name="arguments"></a><span data-ttu-id="8f2f1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8f2f1-105">Arguments</span></span>

`response_file`  
<span data-ttu-id="8f2f1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-106">Required.</span></span> <span data-ttu-id="8f2f1-107">Hierbei handelt es sich um eine Datei, die Compileroptionen oder zu kompilierende Quellcodedateien auflistet.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="8f2f1-108">Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f2f1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f2f1-109">Remarks</span></span>

<span data-ttu-id="8f2f1-110">Die in einer Antwortdatei angegebenen Compileroptionen und Quellcodedateien werden vom Compiler so verarbeitet, als wären sie in der Befehlszeile angegeben.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>

<span data-ttu-id="8f2f1-111">Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Antwortdateioptionen an, z. B. die folgenden:</span><span class="sxs-lookup"><span data-stu-id="8f2f1-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>

```console
@file1.rsp @file2.rsp
```

<span data-ttu-id="8f2f1-112">In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="8f2f1-113">Eine einzelne Compileroption muss in einer Zeile angegeben werden (und darf nicht mehrere Zeilen umfassen).</span><span class="sxs-lookup"><span data-stu-id="8f2f1-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="8f2f1-114">Antwortdateien können Kommentare aufweisen, die mit einem `#`-Symbol beginnen.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-114">Response files can have comments that begin with the `#` symbol.</span></span>

<span data-ttu-id="8f2f1-115">Sie können in der Befehlszeile angegebene Optionen mit Optionen kombinieren, die in einer oder mehreren Antwortdateien angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="8f2f1-116">Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge, in der sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="8f2f1-117">Daher können Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="8f2f1-118">Umgekehrt setzen Optionen in einer Antwortdatei zuvor in der Befehlszeile oder in anderen Antwortdateien aufgeführte Optionen außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>

<span data-ttu-id="8f2f1-119">Visual Basic stellt die Datei „Vbc.rsp“ bereit, die sich im selben Verzeichnis wie die Datei „Vbc.exe“ befindet.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="8f2f1-120">Die Datei „Vbc.rsp“ ist standardmäßig enthalten, es sei denn, die Option `-noconfig` wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="8f2f1-121">Weitere Informationen finden Sie unter [-noconfig](noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="8f2f1-121">For more information, see [-noconfig](noconfig.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8f2f1-122">Die Option `@` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="8f2f1-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f2f1-123">Example</span></span>

<span data-ttu-id="8f2f1-124">Die folgenden Zeilen stammen aus einer Beispielantwortdatei.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-124">The following lines are from a sample response file.</span></span>

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a><span data-ttu-id="8f2f1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f2f1-125">Example</span></span>

<span data-ttu-id="8f2f1-126">Im folgenden Beispiel wird die Verwendung der Option `@` mit der Antwortdatei mit dem Namen `File1.rsp` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8f2f1-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>

```console
vbc @file1.rsp
```

## <a name="see-also"></a><span data-ttu-id="8f2f1-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f2f1-127">See also</span></span>

- [<span data-ttu-id="8f2f1-128">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="8f2f1-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="8f2f1-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="8f2f1-129">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="8f2f1-130">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="8f2f1-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
