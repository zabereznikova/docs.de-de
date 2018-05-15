---
title: -recurse (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 7d18fb2b1710e074653e054d003be762d947d1be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="84e1e-102">-recurse (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="84e1e-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="84e1e-103">Mit der Option „-recurse“ können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (dir) oder des Projektverzeichnisses kompilieren.</span><span class="sxs-lookup"><span data-stu-id="84e1e-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e1e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84e1e-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="84e1e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="84e1e-105">Arguments</span></span>  
 <span data-ttu-id="84e1e-106">`dir` (optional)</span><span class="sxs-lookup"><span data-stu-id="84e1e-106">`dir` (optional)</span></span>  
 <span data-ttu-id="84e1e-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="84e1e-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="84e1e-108">Wenn dieses nicht angegeben wird, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="84e1e-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="84e1e-109">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="84e1e-109">The file(s) to search for.</span></span> <span data-ttu-id="84e1e-110">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="84e1e-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e1e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84e1e-111">Remarks</span></span>  
 <span data-ttu-id="84e1e-112">Mit der Option **-recurse** können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (`dir`) oder des Projektverzeichnisses kompilieren.</span><span class="sxs-lookup"><span data-stu-id="84e1e-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="84e1e-113">Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne **-recurse** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="84e1e-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="84e1e-114">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="84e1e-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84e1e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="84e1e-115">Example</span></span>  
 <span data-ttu-id="84e1e-116">Kompiliert alle C#-Dateien im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="84e1e-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="84e1e-117">Kompiliert alle C#-Dateien im Verzeichnis „dir1\dir2“ sowie in allen Verzeichnisse darunter und generiert „dir2.dll“:</span><span class="sxs-lookup"><span data-stu-id="84e1e-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="84e1e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e1e-118">See Also</span></span>  
 [<span data-ttu-id="84e1e-119">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="84e1e-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="84e1e-120">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="84e1e-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
