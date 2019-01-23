---
title: -Nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 1b9cedc3e45795a66c203d4c86bb071045a1d3f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550473"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="2ce0f-102">-Nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ce0f-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="2ce0f-103">Unterdrückt die Anzeige der Copyrightinformationen und informationsmeldungen während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="2ce0f-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce0f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ce0f-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="2ce0f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ce0f-105">Remarks</span></span>  
 <span data-ttu-id="2ce0f-106">Bei Angabe von `-nologo`, der Compiler nicht Copyrightinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ce0f-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="2ce0f-107">In der Standardeinstellung ist `-nologo` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="2ce0f-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ce0f-108">Die `-nologo` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="2ce0f-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ce0f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ce0f-109">Example</span></span>  
 <span data-ttu-id="2ce0f-110">Der folgende code kompiliert `T2.vb` und Copyrightinformationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ce0f-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ce0f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ce0f-111">See also</span></span>
- [<span data-ttu-id="2ce0f-112">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="2ce0f-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2ce0f-113">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="2ce0f-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
