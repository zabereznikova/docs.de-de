---
title: -Nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 011c9499eaa728588e6181e33a96dd75b4a7b84b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="26ed2-102">-Nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26ed2-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="26ed2-103">Unterdrückt die Anzeige der Copyrightinformationen und informationsmeldungen während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="26ed2-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ed2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26ed2-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="26ed2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26ed2-105">Remarks</span></span>  
 <span data-ttu-id="26ed2-106">Bei Angabe von `-nologo`, der Compiler eine Copyrightinformationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26ed2-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="26ed2-107">In der Standardeinstellung ist `-nologo` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="26ed2-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26ed2-108">Die `-nologo` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="26ed2-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26ed2-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26ed2-109">Example</span></span>  
 <span data-ttu-id="26ed2-110">Der folgende code kompiliert `T2.vb` und Copyrightinformationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26ed2-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="26ed2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26ed2-111">See Also</span></span>  
 [<span data-ttu-id="26ed2-112">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="26ed2-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="26ed2-113">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="26ed2-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
