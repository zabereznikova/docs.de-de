---
title: -Recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 1edb648ec574c0052b7b8314f4ada710c8b0fe01
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183333"
---
# <a name="-recurse"></a><span data-ttu-id="f0c2b-102">-Recurse</span><span class="sxs-lookup"><span data-stu-id="f0c2b-102">-recurse</span></span>
<span data-ttu-id="f0c2b-103">Kompiliert Quellcode-Dateien in allen untergeordneten Verzeichnissen im angegebenen Verzeichnis oder dem Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0c2b-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f0c2b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f0c2b-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="f0c2b-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-106">Optional.</span></span> <span data-ttu-id="f0c2b-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="f0c2b-108">Wenn nicht angegeben ist, beginnt die Suche, im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="f0c2b-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-109">Required.</span></span> <span data-ttu-id="f0c2b-110">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-110">The file(s) to search for.</span></span> <span data-ttu-id="f0c2b-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0c2b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0c2b-112">Remarks</span></span>  
 <span data-ttu-id="f0c2b-113">Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne mit `-recurse`.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="f0c2b-114">Wenn kein Dateiname für die Ausgabe angegeben wird, basiert der Compiler den Ausgabedateinamen auf der ersten Eingabedatei verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="f0c2b-115">Dies ist in der Regel die erste Datei in der Liste der Dateien, die kompiliert, wenn alphabetisch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="f0c2b-116">Aus diesem Grund ist es am besten, geben Sie eine Ausgabe mit der `-out` Option.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0c2b-117">Die `-recurse` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c2b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0c2b-118">Example</span></span>  
 <span data-ttu-id="f0c2b-119">Der folgende Befehl kompiliert, alle Visual Basic-Dateien im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="f0c2b-120">Der folgende Befehl kompiliert, alle Visual Basic-Dateien in die `Test\ABC` Verzeichnis und allen Verzeichnisse darunter, und generiert dann `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="f0c2b-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0c2b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0c2b-121">See Also</span></span>  
 [<span data-ttu-id="f0c2b-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f0c2b-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f0c2b-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0c2b-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="f0c2b-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f0c2b-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
