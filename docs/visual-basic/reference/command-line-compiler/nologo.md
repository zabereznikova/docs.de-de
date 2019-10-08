---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: bb64a468f67745b80b47b42c4fac18852279035d
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005424"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="d7a20-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7a20-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="d7a20-103">Unterdrückt die Anzeige der Copyright Banner und Informationsmeldungen während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="d7a20-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7a20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7a20-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="d7a20-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7a20-105">Remarks</span></span>  
 <span data-ttu-id="d7a20-106">Wenn Sie `-nologo` angeben, wird vom Compiler kein Copyright Banner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7a20-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="d7a20-107">In der Standardeinstellung ist `-nologo` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="d7a20-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a20-108">Die Option "`-nologo`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="d7a20-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7a20-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7a20-109">Example</span></span>  
 <span data-ttu-id="d7a20-110">Mit dem folgenden Code wird `T2.vb` kompiliert, und es wird kein Copyright Banner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7a20-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7a20-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7a20-111">See also</span></span>

- [<span data-ttu-id="d7a20-112">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d7a20-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d7a20-113">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d7a20-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
