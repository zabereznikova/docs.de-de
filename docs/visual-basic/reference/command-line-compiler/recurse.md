---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a><span data-ttu-id="d0f16-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="d0f16-102">/recurse</span></span>
<span data-ttu-id="d0f16-103">Kompiliert Quellcode Dateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnis oder das Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d0f16-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0f16-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0f16-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d0f16-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="d0f16-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d0f16-106">Optional.</span></span> <span data-ttu-id="d0f16-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="d0f16-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="d0f16-108">Wenn nicht angegeben wird, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d0f16-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="d0f16-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d0f16-109">Required.</span></span> <span data-ttu-id="d0f16-110">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0f16-110">The file(s) to search for.</span></span> <span data-ttu-id="d0f16-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d0f16-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0f16-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0f16-112">Remarks</span></span>  
 <span data-ttu-id="d0f16-113">Sie können Platzhalter in einem Dateinamen verwenden, kompilieren Sie alle entsprechende Dateien im Projektverzeichnis ohne `/recurse`.</span><span class="sxs-lookup"><span data-stu-id="d0f16-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="d0f16-114">Wenn kein Dateiname der Ausgabe angegeben wird, basiert der Compiler den Namen der Ausgabedatei für den ersten Eingabedatei verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d0f16-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="d0f16-115">Dies ist normalerweise die erste Datei in der Liste der Dateien, die kompiliert wird, wenn Sie in alphabetischer Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0f16-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="d0f16-116">Aus diesem Grund ist es am besten, geben Sie eine Ausgabe mit der `/out` Option.</span><span class="sxs-lookup"><span data-stu-id="d0f16-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0f16-117">Die `/recurse` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="d0f16-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f16-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0f16-118">Example</span></span>  
 <span data-ttu-id="d0f16-119">Der folgende Code kompiliert wird, alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d0f16-119">The following code compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="d0f16-120">Der folgende Code kompiliert wird, alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien in der `Test\ABC` Verzeichnis und alle Verzeichnisse darunter und generiert dann `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="d0f16-120">The following code compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0f16-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0f16-121">See Also</span></span>  
 [<span data-ttu-id="d0f16-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d0f16-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d0f16-123">/ out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0f16-123">/out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="d0f16-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d0f16-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
