---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002361"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="4229e-102">-Codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4229e-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="4229e-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="4229e-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4229e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4229e-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="4229e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4229e-105">Arguments</span></span>  
  
|<span data-ttu-id="4229e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4229e-106">Term</span></span>|<span data-ttu-id="4229e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4229e-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="4229e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4229e-108">Required.</span></span> <span data-ttu-id="4229e-109">Der Compiler verwendet die durch `id` angegebene Codepage, um die Codierung der Quelldateien zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="4229e-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4229e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4229e-110">Remarks</span></span>  
 <span data-ttu-id="4229e-111">Zum Kompilieren von Quellcode, der mit einer bestimmten Codierung gespeichert wird, können Sie mit `-codepage` angeben, welche Codepage verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4229e-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="4229e-112">Die Option "`-codepage`" gilt für alle Quell Code Dateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="4229e-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="4229e-113">Weitere Informationen finden Sie unter [Zeichencodierung in der .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="4229e-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="4229e-114">Die Option "`-codepage`" ist nicht erforderlich, wenn die Quell Code Dateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="4229e-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="4229e-115">Visual Studio speichert alle Quell Code Dateien standardmäßig mit der aktuellen ANSI-Codepage, es sei denn, der Benutzer gibt im **Codierungs** Dialogfeld eine andere Codierung an.</span><span class="sxs-lookup"><span data-stu-id="4229e-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="4229e-116">Visual Studio verwendet das Dialogfeld **Codierung** , um Quell Code Dateien zu öffnen, die mit einer anderen Codepage gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4229e-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4229e-117">Die Option "`-codepage`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4229e-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4229e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4229e-118">See also</span></span>

- [<span data-ttu-id="4229e-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4229e-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
