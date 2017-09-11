---
title: -recurse (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a><span data-ttu-id="c849e-102">/recurse (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="c849e-102">/recurse (C# Compiler Options)</span></span>
<span data-ttu-id="c849e-103">Mit der Option „/recurse“ können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (dir) oder des Projektverzeichnisses kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c849e-103">The /recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c849e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c849e-104">Syntax</span></span>  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="c849e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c849e-105">Arguments</span></span>  
 <span data-ttu-id="c849e-106">`dir` (optional)</span><span class="sxs-lookup"><span data-stu-id="c849e-106">`dir` (optional)</span></span>  
 <span data-ttu-id="c849e-107">Das Verzeichnis, in dem die Suche beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="c849e-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="c849e-108">Wenn dieses nicht angegeben wird, beginnt die Suche im Projektverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c849e-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="c849e-109">Die Datei(en), nach der oder denen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c849e-109">The file(s) to search for.</span></span> <span data-ttu-id="c849e-110">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c849e-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c849e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c849e-111">Remarks</span></span>  
 <span data-ttu-id="c849e-112">Mit der Option **/recurse** können Sie Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses (`dir`) oder des Projektverzeichnisses kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c849e-112">The **/recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="c849e-113">Sie können Platzhalter in einem Dateinamen verwenden, um alle übereinstimmenden Dateien im Projektverzeichnis zu kompilieren, ohne **/recurse** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c849e-113">You can use wildcards in a file name to compile all matching files in the project directory without using **/recurse**.</span></span>  
  
 <span data-ttu-id="c849e-114">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="c849e-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c849e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c849e-115">Example</span></span>  
 <span data-ttu-id="c849e-116">Kompiliert alle C#-Dateien im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c849e-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="c849e-117">Kompiliert alle C#-Dateien im Verzeichnis „dir1\dir2“ sowie in allen Verzeichnisse darunter und generiert „dir2.dll“:</span><span class="sxs-lookup"><span data-stu-id="c849e-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c849e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c849e-118">See Also</span></span>  
 <span data-ttu-id="c849e-119">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="c849e-119">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="c849e-120">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="c849e-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

