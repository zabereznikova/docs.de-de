---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: a38fb4be9347b3372b4a459fce2e96b9e38c3a51
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343544"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="6dab8-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6dab8-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="6dab8-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="6dab8-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dab8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dab8-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="6dab8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6dab8-105">Arguments</span></span>  
  
|<span data-ttu-id="6dab8-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="6dab8-106">Term</span></span>|<span data-ttu-id="6dab8-107">Definition</span><span class="sxs-lookup"><span data-stu-id="6dab8-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="6dab8-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6dab8-108">Required.</span></span> <span data-ttu-id="6dab8-109">Der Compiler verwendet die von `id` angegebene Codepage, um die Codierung der Quelldateien zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="6dab8-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dab8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6dab8-110">Remarks</span></span>  
 <span data-ttu-id="6dab8-111">Sie können `-codepage` verwenden, um anzugeben, welche Codepage verwendet werden soll, um Quellcode zu kompilieren, der mit einer bestimmten Codierung gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="6dab8-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="6dab8-112">Die Option `-codepage` wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.</span><span class="sxs-lookup"><span data-stu-id="6dab8-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="6dab8-113">Weitere Informationen finden Sie unter [Verwendung von Zeichencodierungsklassen in .NET](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="6dab8-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="6dab8-114">Die Option `-codepage` ist nicht erforderlich, wenn die Quellcodedateien unter Verwendung der aktuellen Version der ANSI-Codepage, von Unicode oder von UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="6dab8-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="6dab8-115">In Visual Studio werden alle Quellcodedateien standardmäßig mit der aktuellen ANSI-Codepage gespeichert, es sei denn, der Benutzer gibt im Dialogfeld **Codierung** eine andere Codierung an.</span><span class="sxs-lookup"><span data-stu-id="6dab8-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="6dab8-116">Visual Studio verwendet das Dialogfeld **Codierung**, um Quellcodedateien zu öffnen, die mit einer anderen Codepage gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="6dab8-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6dab8-117">Die Option `-codepage` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6dab8-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dab8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dab8-118">See also</span></span>

- [<span data-ttu-id="6dab8-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6dab8-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
