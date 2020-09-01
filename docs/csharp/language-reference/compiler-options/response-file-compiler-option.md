---
description: '@ (C#-Compileroptionen)'
title: '@ (C#-Compileroptionen)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: 89a057cba6e0d23c15fc9b652e5bfbc89b6ecbaa
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128646"
---
# <a name="-c-compiler-options"></a><span data-ttu-id="6dcde-103">@ (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="6dcde-103">@ (C# Compiler Options)</span></span>
<span data-ttu-id="6dcde-104">Mit der @-Option können Sie eine Datei angeben, die Compileroptionen und zu kompilierende Quellcodedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="6dcde-104">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dcde-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dcde-105">Syntax</span></span>  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6dcde-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="6dcde-106">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="6dcde-107">Eine Datei, die Compileroptionen oder zu kompilierende Quellcodedateien auflistet.</span><span class="sxs-lookup"><span data-stu-id="6dcde-107">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dcde-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6dcde-108">Remarks</span></span>  
 <span data-ttu-id="6dcde-109">Die Compileroptionen und Quellcodedateien werden vom Compiler so verarbeitet, als ob sie in der Befehlszeile angegeben wären.</span><span class="sxs-lookup"><span data-stu-id="6dcde-109">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="6dcde-110">Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Antwortdateioptionen an.</span><span class="sxs-lookup"><span data-stu-id="6dcde-110">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="6dcde-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6dcde-111">For example:</span></span>  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="6dcde-112">In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6dcde-112">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="6dcde-113">Eine einzelne Compileroption muss in einer Zeile angegeben werden (und darf nicht mehrere Zeilen umfassen).</span><span class="sxs-lookup"><span data-stu-id="6dcde-113">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="6dcde-114">Antwortdateien können Kommentare aufweisen, die mit einem #-Symbol beginnen.</span><span class="sxs-lookup"><span data-stu-id="6dcde-114">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="6dcde-115">Die Angabe von Compileroptionen innerhalb einer Antwortdatei entspricht dem Ausgeben von Befehlen in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="6dcde-115">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="6dcde-116">Weitere Informationen finden Sie unter [Erstellen von der Befehlszeile aus](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="6dcde-116">See [Building from the Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="6dcde-117">Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge, in der sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="6dcde-117">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="6dcde-118">Daher können Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6dcde-118">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="6dcde-119">Im Gegensatz dazu überschreiben Optionen in einer Antwortdatei zuvor in der Befehlszeile oder in anderen Antwortdateien aufgeführte Optionen.</span><span class="sxs-lookup"><span data-stu-id="6dcde-119">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="6dcde-120">C# stellt die Datei „csc.rsp“ bereit, die sich im selben Verzeichnis wie die Datei „csc.exe“ befindet.</span><span class="sxs-lookup"><span data-stu-id="6dcde-120">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="6dcde-121">Weitere Informationen zu „csc.rsp“ finden Sie unter [-noconfig](./noconfig-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6dcde-121">See [-noconfig](./noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="6dcde-122">Diese Compileroption kann weder in der Visual Studio-Entwicklungsumgebung festgelegt werden, noch kann sie programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6dcde-122">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dcde-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6dcde-123">Example</span></span>  
 <span data-ttu-id="6dcde-124">Nachfolgend sind einige Zeilen aus einer Beispielantwortdatei aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="6dcde-124">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="6dcde-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6dcde-125">See also</span></span>

- [<span data-ttu-id="6dcde-126">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="6dcde-126">C# Compiler Options</span></span>](./index.md)
