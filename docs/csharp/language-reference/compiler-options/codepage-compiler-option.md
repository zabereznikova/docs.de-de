---
title: -codepage (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
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
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a><span data-ttu-id="1b3de-102">/codepage (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="1b3de-102">/codepage (C# Compiler Options)</span></span>
<span data-ttu-id="1b3de-103">Diese Option gibt an, welche Codepage beim Kompilieren verwendet werden soll, wenn die erforderliche Seite nicht die aktuelle Standardcodepage für das System ist.</span><span class="sxs-lookup"><span data-stu-id="1b3de-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b3de-104">Syntax</span></span>  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b3de-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1b3de-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="1b3de-106">Die ID der Codepage, die für alle Quellcodedateien in der Kompilierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b3de-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b3de-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b3de-107">Remarks</span></span>  
 <span data-ttu-id="1b3de-108">Wenn Sie eine oder mehrere Quellcodedateien kompilieren, für die beim Erstellen nicht die Verwendung der Standardcodepage auf dem Computer festgelegt wurde, können Sie die Option **/codepage** verwenden, um anzugeben, welche Codeseite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b3de-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **/codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="1b3de-109">**/codepage** wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.</span><span class="sxs-lookup"><span data-stu-id="1b3de-109">**/codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="1b3de-110">Wenn die Quellcodedateien mit der auf dem Computer aktivierten Codepage oder mit UNICODE bzw. UTF-8 erstellt wurden, müssen Sie **/codepage** nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b3de-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **/codepage**.</span></span>  
  
 <span data-ttu-id="1b3de-111">Weitere Informationen darüber, wie ermittelt wird, welche Codeseiten auf dem System unterstützt werden, finden Sie unter [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371).</span><span class="sxs-lookup"><span data-stu-id="1b3de-111">See [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="1b3de-112">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="1b3de-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3de-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b3de-113">See Also</span></span>  
 <span data-ttu-id="1b3de-114">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="1b3de-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="1b3de-115">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="1b3de-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

