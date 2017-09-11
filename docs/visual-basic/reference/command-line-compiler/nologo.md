---
title: / nologo (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners, suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe03c36f46717248269c9aaec13b40569161b0e0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="nologo-visual-basic"></a><span data-ttu-id="e601d-102">/nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e601d-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="e601d-103">Unterdrückt die Anzeige der Copyrightinformationen und informative Nachrichten während der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="e601d-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e601d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e601d-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="e601d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e601d-105">Remarks</span></span>  
 <span data-ttu-id="e601d-106">Bei Angabe von `/nologo`, der Compiler nicht Copyrightinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e601d-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="e601d-107">In der Standardeinstellung ist `/nologo` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="e601d-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e601d-108">Die `/nologo` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="e601d-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e601d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e601d-109">Example</span></span>  
 <span data-ttu-id="e601d-110">Der folgende code kompiliert `T2.vb` und Copyrightinformationen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e601d-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e601d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e601d-111">See Also</span></span>  
 <span data-ttu-id="e601d-112">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e601d-112">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e601d-113"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="e601d-113"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
