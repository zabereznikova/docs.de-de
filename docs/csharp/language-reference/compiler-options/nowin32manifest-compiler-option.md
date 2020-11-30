---
description: -nowin32manifest (C#-Compileroptionen)
title: -nowin32manifest (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 13bbee66901149d54632d9b164431f8898cdf52e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193997"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="21a7f-103">-nowin32manifest (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="21a7f-103">-nowin32manifest (C# Compiler Options)</span></span>

<span data-ttu-id="21a7f-104">Verwenden Sie die Option **-nowin32manifest**, um den Compiler anzuweisen, kein Anwendungsmanifest in die ausführbare Datei einzubetten.</span><span class="sxs-lookup"><span data-stu-id="21a7f-104">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a7f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="21a7f-105">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="21a7f-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21a7f-106">Remarks</span></span>  

 <span data-ttu-id="21a7f-107">Wenn diese Option verwendet wird, unterliegt die Anwendung der Virtualisierung unter Windows Vista, es sei denn, Sie stellen ein Anwendungsmanifest in einer Win32-Ressourcendatei oder einem späteren Buildschritt bereit.</span><span class="sxs-lookup"><span data-stu-id="21a7f-107">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="21a7f-108">Legen Sie diese Option in Visual Studio auf der Seite **Application Property** (Anwendungseigenschaft) fest, indem Sie in der **Manifest**-Dropdownliste auf die Option **Create Application Without a Manifest** (Anwendung ohne ein Manifest erstellen) klicken.</span><span class="sxs-lookup"><span data-stu-id="21a7f-108">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="21a7f-109">Weitere Informationen finden Sie unter [Seite „Anwendung“, Projekt-Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="21a7f-109">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="21a7f-110">Weitere Informationen zum Erstellen von Manifesten finden Sie unter [-win32manifest (C#-Compileroptionen)](./win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="21a7f-110">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a7f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21a7f-111">See also</span></span>

- [<span data-ttu-id="21a7f-112">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="21a7f-112">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="21a7f-113">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="21a7f-113">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
