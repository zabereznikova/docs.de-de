---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082199"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="09e30-102">-Codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09e30-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="09e30-103">Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.</span><span class="sxs-lookup"><span data-stu-id="09e30-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09e30-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="09e30-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="09e30-105">Arguments</span></span>  
  
|<span data-ttu-id="09e30-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="09e30-106">Term</span></span>|<span data-ttu-id="09e30-107">Definition</span><span class="sxs-lookup"><span data-stu-id="09e30-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="09e30-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="09e30-108">Required.</span></span> <span data-ttu-id="09e30-109">Der Compiler verwendet die Codepage, die anhand des `id` interpretiert die Codierung der Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="09e30-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09e30-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09e30-110">Remarks</span></span>  
 <span data-ttu-id="09e30-111">Zum Kompilieren von Quellcode mit einer bestimmten Codierung gespeichert, können Sie `-codepage` angeben, welche Codeseite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="09e30-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="09e30-112">Die `-codepage` Option gilt für alle Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="09e30-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="09e30-113">Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="09e30-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="09e30-114">Die `-codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="09e30-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="09e30-115">Visual Studio speichert alle Quellcodedateien mit der aktuellen ANSI-Codepage in der Standardeinstellung, wenn der Benutzer gibt eine andere Codierung der **Codierung** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="09e30-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="09e30-116">Visual Studio verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode-Dateien, die mit einer anderen Codepage gespeichert.</span><span class="sxs-lookup"><span data-stu-id="09e30-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09e30-117">Die `-codepage` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="09e30-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e30-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09e30-118">See also</span></span>

- [<span data-ttu-id="09e30-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="09e30-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
