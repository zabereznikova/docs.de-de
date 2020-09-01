---
description: -codepage (C#-Compileroptionen)
title: -codepage (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 4c812314ed9c1abcd7d2f34b2281140175621312
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125955"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="27f4c-103">-codepage (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="27f4c-103">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="27f4c-104">Diese Option gibt an, welche Codepage beim Kompilieren verwendet werden soll, wenn die erforderliche Seite nicht die aktuelle Standardcodepage für das System ist.</span><span class="sxs-lookup"><span data-stu-id="27f4c-104">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27f4c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="27f4c-105">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="27f4c-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="27f4c-106">Arguments</span></span>  
 `id`  
 <span data-ttu-id="27f4c-107">Die ID der Codepage, die für alle Quellcodedateien in der Kompilierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="27f4c-107">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27f4c-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="27f4c-108">Remarks</span></span>  
 <span data-ttu-id="27f4c-109">Der Compiler versucht zunächst, alle Quelldateien als UTF-8 zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="27f4c-109">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="27f4c-110">Wenn Ihre Quellcodedateien eine andere Codierung als UTF-8 aufweisen und andere Zeichen als 7-Bit-ASCII-Zeichen verwendet werden, sollten Sie mit der Option **-codepage** angeben, welche Codeseite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="27f4c-110">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="27f4c-111">**-codepage** wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.</span><span class="sxs-lookup"><span data-stu-id="27f4c-111">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="27f4c-112">Weitere Informationen darüber, wie ermittelt wird, welche Codeseiten auf dem System unterstützt werden, finden Sie unter [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).</span><span class="sxs-lookup"><span data-stu-id="27f4c-112">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="27f4c-113">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="27f4c-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f4c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27f4c-114">See also</span></span>

- [<span data-ttu-id="27f4c-115">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="27f4c-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="27f4c-116">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="27f4c-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
