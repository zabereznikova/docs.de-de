---
title: / recurse | Microsoft-Dokumentation
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
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
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
ms.openlocfilehash: 9ceb2f3bc9e4d0f1088258f504b7a49c58a29e35
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="recurse"></a><span data-ttu-id="74ef3-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="74ef3-102">/recurse</span></span>
<span data-ttu-id="74ef3-103">Kompiliert Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="74ef3-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ef3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74ef3-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="74ef3-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="74ef3-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="74ef3-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="74ef3-106">Optional.</span></span> <span data-ttu-id="74ef3-107">Das Verzeichnis, in dem Sie die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="74ef3-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="74ef3-108">Wenn nicht angegeben, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="74ef3-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="74ef3-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74ef3-109">Required.</span></span> <span data-ttu-id="74ef3-110">Die zu suchenden Dateien.</span><span class="sxs-lookup"><span data-stu-id="74ef3-110">The file(s) to search for.</span></span> <span data-ttu-id="74ef3-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="74ef3-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74ef3-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74ef3-112">Remarks</span></span>  
 <span data-ttu-id="74ef3-113">Sie können Platzhalter in einem Dateinamen verwenden, kompilieren Sie alle entsprechende Dateien im Projektverzeichnis ohne `/recurse`.</span><span class="sxs-lookup"><span data-stu-id="74ef3-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="74ef3-114">Wenn kein Ausgabedateiname angegeben wird, basiert der Compiler den Namen der Ausgabedatei der ersten Eingabedatei verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="74ef3-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="74ef3-115">Dies ist normalerweise die erste Datei in der Liste der Dateien, die kompiliert, wenn alphabetisch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74ef3-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="74ef3-116">Aus diesem Grund empfiehlt sich, geben Sie eine Ausgabe mit den `/out` Option.</span><span class="sxs-lookup"><span data-stu-id="74ef3-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74ef3-117">Die `/recurse` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="74ef3-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74ef3-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74ef3-118">Example</span></span>  
 <span data-ttu-id="74ef3-119">Der folgende Code kompiliert werden alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="74ef3-119">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="74ef3-120">Der folgende Code kompiliert alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien in der `Test\ABC` Verzeichnis und in allen Verzeichnissen unter, und generiert dann `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="74ef3-120">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="74ef3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74ef3-121">See Also</span></span>  
 <span data-ttu-id="74ef3-122">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="74ef3-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="74ef3-123"> [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span><span class="sxs-lookup"><span data-stu-id="74ef3-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span></span>  
<span data-ttu-id="74ef3-124"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="74ef3-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
