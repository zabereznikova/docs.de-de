---
title: -Langversion (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b91bf8efa6fabd21d257e51062dc881ab288f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="d82b0-102">-Langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d82b0-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="d82b0-103">Bewirkt, dass der Compiler nur Syntax akzeptiert, die in der angegebenen Version der Visual Basic-Sprache enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d82b0-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d82b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d82b0-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="d82b0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d82b0-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="d82b0-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d82b0-106">Required.</span></span> <span data-ttu-id="d82b0-107">Die Sprachversion, die während der Kompilierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d82b0-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="d82b0-108">Gültige Werte sind `9`, `9.0`, `10`, und `10.0`.</span><span class="sxs-lookup"><span data-stu-id="d82b0-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d82b0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d82b0-109">Remarks</span></span>  
 <span data-ttu-id="d82b0-110">Die `-langversion` Option gibt an, welche Syntax der Compiler akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d82b0-110">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="d82b0-111">Wenn Sie angeben, dass die Sprachversion 9.0 ist, generiert der Compiler z. B. Fehler für die Syntax, die nur in Version 10.0 gültig und höher ist.</span><span class="sxs-lookup"><span data-stu-id="d82b0-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="d82b0-112">Sie können diese Option verwenden, wenn Sie Anwendungen, die auf verschiedenen Versionen von .NET Framework entwickeln.</span><span class="sxs-lookup"><span data-stu-id="d82b0-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="d82b0-113">Wenn Sie .NET Framework 3.5 abzielen, konnte Sie z. B. diese Option verwenden, um sicherzustellen, dass Sie die Syntax von, Sprachversion 10.0 nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="d82b0-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="d82b0-114">Sie können festlegen, `-langversion` direkt nur mithilfe der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d82b0-114">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="d82b0-115">Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="d82b0-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d82b0-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d82b0-116">Example</span></span>  
 <span data-ttu-id="d82b0-117">Der folgende code kompiliert `sample.vb` für Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="d82b0-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d82b0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d82b0-118">See Also</span></span>  
 [<span data-ttu-id="d82b0-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="d82b0-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d82b0-120">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="d82b0-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d82b0-121">Festlegen einer bestimmten .NET-Framework-Version</span><span class="sxs-lookup"><span data-stu-id="d82b0-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
