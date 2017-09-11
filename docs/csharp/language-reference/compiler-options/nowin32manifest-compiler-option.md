---
title: -nowin32manifest (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowin32manifest
dev_langs:
- CSharp
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8314fd661ccce968238b480b54847abf7cbece74
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="nowin32manifest-c-compiler-options"></a><span data-ttu-id="3c1d8-102">/nowin32manifest (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="3c1d8-102">/nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="3c1d8-103">Verwenden Sie die Option **/nowin32manifest**, um den Compiler anzuweisen, kein Anwendungsmanifest in die ausführbare Datei einzubetten.</span><span class="sxs-lookup"><span data-stu-id="3c1d8-103">Use the **/nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c1d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c1d8-104">Syntax</span></span>  
  
```console  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="3c1d8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c1d8-105">Remarks</span></span>  
 <span data-ttu-id="3c1d8-106">Wenn diese Option verwendet wird, unterliegt die Anwendung der Virtualisierung unter Windows Vista, es sei denn, Sie stellen ein Anwendungsmanifest in einer Win32-Ressourcendatei oder einem späteren Buildschritt bereit.</span><span class="sxs-lookup"><span data-stu-id="3c1d8-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="3c1d8-107">Legen Sie diese Option in Visual Studio auf der Seite **Application Property** (Anwendungseigenschaft) fest, indem Sie in der **Manifest**-Dropdownliste auf die Option **Create Application Without a Manifest** (Anwendung ohne ein Manifest erstellen) klicken.</span><span class="sxs-lookup"><span data-stu-id="3c1d8-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="3c1d8-108">Weitere Informationen finden Sie unter [Seite „Anwendung“, Projekt-Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="3c1d8-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="3c1d8-109">Weitere Informationen zum Erstellen von Manifesten finden Sie unter [/win32manifest (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="3c1d8-109">For more information about manifest creation, see [/win32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1d8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c1d8-110">See Also</span></span>  
 <span data-ttu-id="3c1d8-111">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c1d8-111">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="3c1d8-112">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="3c1d8-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

