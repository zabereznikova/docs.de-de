---
title: '@ (C#-Compileroptionen)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fbb95e0619857f38260ae74366ba4bb860779530
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-c-compiler-options"></a><span data-ttu-id="f175c-102">@ (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="f175c-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="f175c-103">Mit der @-Option können Sie eine Datei angeben, die Compileroptionen und zu kompilierende Quellcodedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="f175c-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f175c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f175c-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f175c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f175c-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="f175c-106">Eine Datei, die Compileroptionen oder zu kompilierende Quellcodedateien auflistet.</span><span class="sxs-lookup"><span data-stu-id="f175c-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f175c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f175c-107">Remarks</span></span>  
 <span data-ttu-id="f175c-108">Die Compileroptionen und Quellcodedateien werden vom Compiler so verarbeitet, als ob sie in der Befehlszeile angegeben wären.</span><span class="sxs-lookup"><span data-stu-id="f175c-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="f175c-109">Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Antwortdateioptionen an.</span><span class="sxs-lookup"><span data-stu-id="f175c-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="f175c-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f175c-110">For example:</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="f175c-111">In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f175c-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="f175c-112">Eine einzelne Compileroption muss in einer Zeile angegeben werden (und darf nicht mehrere Zeilen umfassen).</span><span class="sxs-lookup"><span data-stu-id="f175c-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="f175c-113">Antwortdateien können Kommentare aufweisen, die mit einem #-Symbol beginnen.</span><span class="sxs-lookup"><span data-stu-id="f175c-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="f175c-114">Die Angabe von Compileroptionen innerhalb einer Antwortdatei entspricht dem Ausgeben von Befehlen in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="f175c-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="f175c-115">Weitere Informationen finden Sie unter [Erstellen von der Befehlszeile aus](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="f175c-115">See [Building from the Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="f175c-116">Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge, in der sie auftreten.</span><span class="sxs-lookup"><span data-stu-id="f175c-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="f175c-117">Daher können Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f175c-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="f175c-118">Im Gegensatz dazu überschreiben Optionen in einer Antwortdatei zuvor in der Befehlszeile oder in anderen Antwortdateien aufgeführte Optionen.</span><span class="sxs-lookup"><span data-stu-id="f175c-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="f175c-119">C# stellt die Datei „csc.rsp“ bereit, die sich im selben Verzeichnis wie die Datei „csc.exe“ befindet.</span><span class="sxs-lookup"><span data-stu-id="f175c-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="f175c-120">Weitere Informationen zu „csc.rsp“ finden Sie unter [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f175c-120">See [-noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="f175c-121">Diese Compileroption kann weder in der Visual Studio-Entwicklungsumgebung festgelegt werden, noch kann sie programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f175c-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f175c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f175c-122">Example</span></span>  
 <span data-ttu-id="f175c-123">Nachfolgend sind einige Zeilen aus einer Beispielantwortdatei aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f175c-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f175c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f175c-124">See Also</span></span>  
 [<span data-ttu-id="f175c-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="f175c-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
