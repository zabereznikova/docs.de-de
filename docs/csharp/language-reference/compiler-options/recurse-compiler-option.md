---
description: -recurse (C#-Compileroptionen)
title: -recurse (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 3edd7e23358bc0569dae6204d519209df1ade290
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124824"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="7cb43-103">-recurse (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="7cb43-103">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="7cb43-104">Mit der Option „-recurse“ können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (dir) oder des Projektverzeichnisses kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7cb43-104">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cb43-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cb43-105">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="7cb43-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="7cb43-106">Arguments</span></span>  
 <span data-ttu-id="7cb43-107">`dir` (optional)</span><span class="sxs-lookup"><span data-stu-id="7cb43-107">`dir` (optional)</span></span>  
 <span data-ttu-id="7cb43-108">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="7cb43-108">The directory in which you want the search to begin.</span></span> <span data-ttu-id="7cb43-109">Wenn dieses nicht angegeben wird, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7cb43-109">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="7cb43-110">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7cb43-110">The file(s) to search for.</span></span> <span data-ttu-id="7cb43-111">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="7cb43-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cb43-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cb43-112">Remarks</span></span>  
 <span data-ttu-id="7cb43-113">Mit der Option **-recurse** können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (`dir`) oder des Projektverzeichnisses kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7cb43-113">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="7cb43-114">Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne **-recurse** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7cb43-114">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="7cb43-115">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="7cb43-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cb43-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7cb43-116">Example</span></span>  
 <span data-ttu-id="7cb43-117">Kompiliert alle C#-Dateien im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="7cb43-117">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="7cb43-118">Kompiliert alle C#-Dateien im Verzeichnis „dir1\dir2“ sowie in allen Verzeichnisse darunter und generiert „dir2.dll“:</span><span class="sxs-lookup"><span data-stu-id="7cb43-118">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cb43-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cb43-119">See also</span></span>

- [<span data-ttu-id="7cb43-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7cb43-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="7cb43-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7cb43-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
