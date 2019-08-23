---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962614"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="83baf-102">-Codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83baf-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="83baf-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="83baf-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83baf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83baf-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="83baf-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="83baf-105">Arguments</span></span>  
  
|<span data-ttu-id="83baf-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="83baf-106">Term</span></span>|<span data-ttu-id="83baf-107">Definition</span><span class="sxs-lookup"><span data-stu-id="83baf-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="83baf-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="83baf-108">Required.</span></span> <span data-ttu-id="83baf-109">Der Compiler verwendet die durch `id` angegebene Codepage, um die Codierung der Quelldateien zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="83baf-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83baf-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83baf-110">Remarks</span></span>  
 <span data-ttu-id="83baf-111">Zum Kompilieren von Quellcode, der mit einer bestimmten Codierung gespeichert wird, `-codepage` können Sie verwenden, um anzugeben, welche Codepage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="83baf-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="83baf-112">Die `-codepage` -Option gilt für alle Quell Code Dateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="83baf-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="83baf-113">Weitere Informationen finden Sie unter [Zeichencodierung in der .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="83baf-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="83baf-114">Die `-codepage` Option ist nicht erforderlich, wenn die Quell Code Dateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="83baf-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="83baf-115">Visual Studio speichert alle Quell Code Dateien standardmäßig mit der aktuellen ANSI-Codepage, es sei denn, der Benutzer gibt im **Codierungs** Dialogfeld eine andere Codierung an.</span><span class="sxs-lookup"><span data-stu-id="83baf-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="83baf-116">Visual Studio verwendet das Dialogfeld **Codierung** , um Quell Code Dateien zu öffnen, die mit einer anderen Codepage gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="83baf-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83baf-117">Die `-codepage` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="83baf-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83baf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83baf-118">See also</span></span>

- [<span data-ttu-id="83baf-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="83baf-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
