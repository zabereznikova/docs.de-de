---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f098dd04b457b7db008788bcfb141af3f69843f8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="c8a80-102">-Codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c8a80-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="c8a80-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="c8a80-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8a80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8a80-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8a80-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c8a80-105">Arguments</span></span>  
  
|<span data-ttu-id="c8a80-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c8a80-106">Term</span></span>|<span data-ttu-id="c8a80-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c8a80-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="c8a80-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c8a80-108">Required.</span></span> <span data-ttu-id="c8a80-109">Der Compiler verwendet die Codepage, die vom angegebenen `id` zur Interpretation der Codierung der Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="c8a80-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8a80-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8a80-110">Remarks</span></span>  
 <span data-ttu-id="c8a80-111">Um mit einer bestimmten Codierung gespeichert Quellcode zu kompilieren, können Sie `-codepage` angeben, welche Codepage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8a80-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="c8a80-112">Die `-codepage` Option gilt für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="c8a80-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="c8a80-113">Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="c8a80-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="c8a80-114">Die `-codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="c8a80-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="c8a80-115">Visual Studio speichert alle Quellcodedateien mit der aktuellen ANSI-Codepage standardmäßig, es sei denn, der Benutzer gibt an, einer anderen Codierung der **Codierung** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c8a80-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="c8a80-116">Visual Studio verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode Dateien, die mit einer anderen Codepage gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c8a80-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8a80-117">Die `-codepage` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c8a80-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8a80-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8a80-118">See Also</span></span>  
 [<span data-ttu-id="c8a80-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="c8a80-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
