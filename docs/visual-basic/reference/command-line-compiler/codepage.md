---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 34dbf36cc79a8c4715cf6a07c57d559e14f40030
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363629"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="cd7af-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd7af-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="cd7af-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="cd7af-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd7af-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="cd7af-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cd7af-105">Arguments</span></span>  
  
|<span data-ttu-id="cd7af-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="cd7af-106">Term</span></span>|<span data-ttu-id="cd7af-107">Definition</span><span class="sxs-lookup"><span data-stu-id="cd7af-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="cd7af-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cd7af-108">Required.</span></span> <span data-ttu-id="cd7af-109">Der Compiler verwendet die von `id` angegebene Codepage, um die Codierung der Quelldateien zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="cd7af-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd7af-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd7af-110">Remarks</span></span>  
 <span data-ttu-id="cd7af-111">Sie können `-codepage` verwenden, um anzugeben, welche Codepage verwendet werden soll, um Quellcode zu kompilieren, der mit einer bestimmten Codierung gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="cd7af-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="cd7af-112">Die Option `-codepage` wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.</span><span class="sxs-lookup"><span data-stu-id="cd7af-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="cd7af-113">Weitere Informationen finden Sie unter [Verwendung von Zeichencodierungsklassen in .NET](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="cd7af-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="cd7af-114">Die Option `-codepage` ist nicht erforderlich, wenn die Quellcodedateien unter Verwendung der aktuellen Version der ANSI-Codepage, von Unicode oder von UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="cd7af-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="cd7af-115">In Visual Studio werden alle Quellcodedateien standardmäßig mit der aktuellen ANSI-Codepage gespeichert, es sei denn, der Benutzer gibt im Dialogfeld **Codierung** eine andere Codierung an.</span><span class="sxs-lookup"><span data-stu-id="cd7af-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="cd7af-116">Visual Studio verwendet das Dialogfeld **Codierung**, um Quellcodedateien zu öffnen, die mit einer anderen Codepage gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="cd7af-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd7af-117">Die Option `-codepage` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="cd7af-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7af-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd7af-118">See also</span></span>

- [<span data-ttu-id="cd7af-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="cd7af-119">Visual Basic Command-Line Compiler</span></span>](index.md)
