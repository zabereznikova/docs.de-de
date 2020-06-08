---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: fc8dfe41ea56531ff34cd5e551ef24d636227e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400499"
---
# <a name="-recurse"></a><span data-ttu-id="8b4e5-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="8b4e5-102">-recurse</span></span>
<span data-ttu-id="8b4e5-103">Kompiliert Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b4e5-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b4e5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8b4e5-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="8b4e5-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-106">Optional.</span></span> <span data-ttu-id="8b4e5-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="8b4e5-108">Wenn nicht angegeben, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="8b4e5-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-109">Required.</span></span> <span data-ttu-id="8b4e5-110">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-110">The file(s) to search for.</span></span> <span data-ttu-id="8b4e5-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b4e5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b4e5-112">Remarks</span></span>  
 <span data-ttu-id="8b4e5-113">Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne `-recurse` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="8b4e5-114">Wird kein Name für die Ausgabedatei angegeben, verwendet der Compiler dafür die erste verarbeitete Eingabedatei.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="8b4e5-115">Dies ist in der Regel die erste Datei in der alphabetisch sortierten Liste der kompilierten Daten.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="8b4e5-116">Daher ist es sinnvoll, eine Ausgabedatei mithilfe der `-out`-Option anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b4e5-117">Die Option `-recurse` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b4e5-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b4e5-118">Example</span></span>  
 <span data-ttu-id="8b4e5-119">Mit dem folgenden Befehl werden alle Visual Basic-Dateien im aktuellen Verzeichnis kompiliert:</span><span class="sxs-lookup"><span data-stu-id="8b4e5-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="8b4e5-120">Mit dem folgenden Befehl werden alle Visual Basic-Dateien im Verzeichnis `Test\ABC` und alle Verzeichnisse darunter kompiliert und anschließend `Test.ABC.dll` generiert.</span><span class="sxs-lookup"><span data-stu-id="8b4e5-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b4e5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b4e5-121">See also</span></span>

- [<span data-ttu-id="8b4e5-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="8b4e5-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="8b4e5-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b4e5-123">-out (Visual Basic)</span></span>](out.md)
- [<span data-ttu-id="8b4e5-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="8b4e5-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
