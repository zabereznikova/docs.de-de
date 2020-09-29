---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 5557d681c5e6901592936efd35b3c552d43e39b0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097669"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="b0f82-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0f82-102">-nologo (Visual Basic)</span></span>

<span data-ttu-id="b0f82-103">Unterdrückt die Anzeige von Copyrightbannern und Informationsmeldungen während der Kompilierung</span><span class="sxs-lookup"><span data-stu-id="b0f82-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0f82-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="b0f82-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0f82-105">Remarks</span></span>  

 <span data-ttu-id="b0f82-106">Wenn Sie `-nologo` angeben, zeigt der Compiler keine Copyrightbanner an.</span><span class="sxs-lookup"><span data-stu-id="b0f82-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="b0f82-107">In der Standardeinstellung ist `-nologo` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="b0f82-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0f82-108">Die Option `-nologo` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b0f82-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0f82-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0f82-109">Example</span></span>  

 <span data-ttu-id="b0f82-110">Mit dem folgenden Code wird `T2.vb` kompiliert und kein Copyrightbanner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0f82-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0f82-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0f82-111">See also</span></span>

- [<span data-ttu-id="b0f82-112">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b0f82-112">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b0f82-113">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b0f82-113">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
