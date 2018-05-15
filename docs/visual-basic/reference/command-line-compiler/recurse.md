---
title: -Recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd5dde46cdea67825b14a6f5fa96a82c8bab8d3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-recurse"></a><span data-ttu-id="0de75-102">-Recurse</span><span class="sxs-lookup"><span data-stu-id="0de75-102">-recurse</span></span>
<span data-ttu-id="0de75-103">Kompiliert Quellcode Dateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnis oder das Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0de75-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0de75-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="0de75-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0de75-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="0de75-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0de75-106">Optional.</span></span> <span data-ttu-id="0de75-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="0de75-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="0de75-108">Wenn nicht angegeben wird, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0de75-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="0de75-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0de75-109">Required.</span></span> <span data-ttu-id="0de75-110">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0de75-110">The file(s) to search for.</span></span> <span data-ttu-id="0de75-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0de75-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0de75-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0de75-112">Remarks</span></span>  
 <span data-ttu-id="0de75-113">Sie können Platzhalter in einem Dateinamen verwenden, kompilieren Sie alle entsprechende Dateien im Projektverzeichnis ohne `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="0de75-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="0de75-114">Wenn kein Dateiname der Ausgabe angegeben wird, basiert der Compiler den Namen der Ausgabedatei für den ersten Eingabedatei verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0de75-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="0de75-115">Dies ist normalerweise die erste Datei in der Liste der Dateien, die kompiliert wird, wenn Sie in alphabetischer Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0de75-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="0de75-116">Aus diesem Grund ist es am besten, geben Sie eine Ausgabe mit der `-out` Option.</span><span class="sxs-lookup"><span data-stu-id="0de75-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0de75-117">Die `-recurse` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="0de75-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0de75-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0de75-118">Example</span></span>  
 <span data-ttu-id="0de75-119">Der folgende Befehl kompiliert alle Visual Basic-Dateien im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0de75-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="0de75-120">Der folgende Befehl kompiliert alle Visual Basic-Dateien in den `Test\ABC` Verzeichnis und alle Verzeichnisse darunter und generiert dann `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="0de75-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0de75-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0de75-121">See Also</span></span>  
 [<span data-ttu-id="0de75-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0de75-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0de75-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0de75-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="0de75-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0de75-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
