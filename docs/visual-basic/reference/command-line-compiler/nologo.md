---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335431"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="64cda-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64cda-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="64cda-103">Unterdrückt die Anzeige von Copyrightbannern und Informationsmeldungen während der Kompilierung</span><span class="sxs-lookup"><span data-stu-id="64cda-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64cda-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64cda-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="64cda-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64cda-105">Remarks</span></span>  
 <span data-ttu-id="64cda-106">Wenn Sie `-nologo` angeben, zeigt der Compiler keine Copyrightbanner an.</span><span class="sxs-lookup"><span data-stu-id="64cda-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="64cda-107">In der Standardeinstellung ist `-nologo` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="64cda-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64cda-108">Die Option `-nologo` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="64cda-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64cda-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64cda-109">Example</span></span>  
 <span data-ttu-id="64cda-110">Mit dem folgenden Code wird `T2.vb` kompiliert und kein Copyrightbanner angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64cda-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="64cda-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64cda-111">See also</span></span>

- [<span data-ttu-id="64cda-112">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="64cda-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="64cda-113">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="64cda-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
