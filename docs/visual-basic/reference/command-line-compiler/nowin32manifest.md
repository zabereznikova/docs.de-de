---
title: /NoWin32Manifest (Visual Basic) | Microsoft-Dokumentation
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
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
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
ms.openlocfilehash: 975711c9ee2e56b3c3c33611dd56eb6dc6082471
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="nowin32manifest-visual-basic"></a><span data-ttu-id="a15c5-102">/nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a15c5-102">/nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="a15c5-103">Weist den Compiler an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.</span><span class="sxs-lookup"><span data-stu-id="a15c5-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a15c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a15c5-104">Syntax</span></span>  
  
```  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="a15c5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a15c5-105">Remarks</span></span>  
 <span data-ttu-id="a15c5-106">Wenn diese Option verwendet wird, wird die Anwendung Virtualisierung unter Windows Vista sein, es sei denn, Sie ein Anwendungsmanifest in einer Win32-Ressourcendatei oder bei einem späteren Buildschritt bereit.</span><span class="sxs-lookup"><span data-stu-id="a15c5-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="a15c5-107">Weitere Informationen zur Virtualisierung finden Sie unter [ClickOnce-Bereitstellung unter Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="a15c5-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="a15c5-108">Weitere Informationen zum Erstellen von Manifesten finden Sie unter [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span><span class="sxs-lookup"><span data-stu-id="a15c5-108">For more information about manifest creation, see [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a15c5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a15c5-109">See Also</span></span>  
 <span data-ttu-id="a15c5-110">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a15c5-110">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a15c5-111"> [Seite „Anwendung“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="a15c5-111"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span></span>
