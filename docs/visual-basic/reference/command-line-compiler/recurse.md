---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 71613af0f1c319801296180d49dbacfedf0ceca4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005260"
---
# <a name="-recurse"></a><span data-ttu-id="c4329-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="c4329-102">-recurse</span></span>
<span data-ttu-id="c4329-103">Kompiliert Quell Code Dateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="c4329-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4329-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4329-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4329-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c4329-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="c4329-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="c4329-106">Optional.</span></span> <span data-ttu-id="c4329-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="c4329-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="c4329-108">Wenn kein Wert angegeben wird, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c4329-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="c4329-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4329-109">Required.</span></span> <span data-ttu-id="c4329-110">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4329-110">The file(s) to search for.</span></span> <span data-ttu-id="c4329-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c4329-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4329-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4329-112">Remarks</span></span>  
 <span data-ttu-id="c4329-113">Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne `-recurse` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4329-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="c4329-114">Wenn kein Ausgabe Dateiname angegeben ist, wird der Name der Ausgabedatei von dem Compiler auf der ersten verarbeiteten Eingabedatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c4329-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="c4329-115">Dies ist im Allgemeinen die erste Datei in der Liste der Dateien, die bei der alphabetischen Anzeige kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="c4329-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="c4329-116">Aus diesem Grund empfiehlt es sich, eine Ausgabedatei mithilfe der Option "`-out`" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c4329-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4329-117">Die Option "`-recurse`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c4329-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4329-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4329-118">Example</span></span>  
 <span data-ttu-id="c4329-119">Der folgende Befehl kompiliert alle Visual Basic Dateien im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c4329-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="c4329-120">Der folgende Befehl kompiliert alle Visual Basic Dateien im Verzeichnis "`Test\ABC`" und alle Verzeichnisse darunter und generiert dann `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="c4329-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4329-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4329-121">See also</span></span>

- [<span data-ttu-id="c4329-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c4329-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c4329-123">-Out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4329-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="c4329-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="c4329-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
