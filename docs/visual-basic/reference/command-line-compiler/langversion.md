---
title: / langversion (Visual Basic) | Microsoft-Dokumentation
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
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
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
ms.openlocfilehash: 56411df907bd5ff0416e6d0539cbe46df3b34947
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="langversion-visual-basic"></a><span data-ttu-id="b1112-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1112-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="b1112-103">Bewirkt, dass den Compiler nur Syntax akzeptiert, die in der angegebenen Version der Visual Basic-Sprache enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b1112-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1112-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1112-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="b1112-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b1112-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="b1112-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b1112-106">Required.</span></span> <span data-ttu-id="b1112-107">Die Sprachversion, die während der Kompilierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1112-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="b1112-108">Gültige Werte sind `9`, `9.0`, `10`, und `10.0`.</span><span class="sxs-lookup"><span data-stu-id="b1112-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1112-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1112-109">Remarks</span></span>  
 <span data-ttu-id="b1112-110">Die `/langversion` Option gibt an, welche Syntax der Compiler akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b1112-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="b1112-111">Wenn Sie angeben, dass die Version 9.0 ist, generiert der Compiler z. B. Fehler für Syntax, die nur in Version 10.0 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="b1112-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="b1112-112">Wenn Sie Anwendungen, die verschiedene Versionen von .NET Framework abzielen entwickeln, können Sie diese Option verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1112-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="b1112-113">Wenn Sie .NET Framework 3.5 abzielen, konnte Sie z. B. diese Option verwenden, um sicherzustellen, dass Sie keine Syntax aus der Sprachversion 10.0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1112-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="b1112-114">Sie können festlegen, `/langversion` direkt nur in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b1112-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="b1112-115">Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="b1112-115">For more information, see [Targeting a Specific .NET Framework Version](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1112-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1112-116">Example</span></span>  
 <span data-ttu-id="b1112-117">Der folgende code kompiliert `sample.vb` für Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="b1112-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1112-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1112-118">See Also</span></span>  
 <span data-ttu-id="b1112-119">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b1112-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b1112-120"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="b1112-120"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="b1112-121"> [Festlegen einer bestimmten .NET-Framework-Zielversion](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)</span><span class="sxs-lookup"><span data-stu-id="b1112-121"> [Targeting a Specific .NET Framework Version](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)</span></span>
