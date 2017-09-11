---
title: / moduleassemblyname | Microsoft-Dokumentation
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
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
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
ms.openlocfilehash: 6852b8a0d9874fd65e93cdd9507fe9b7119ce5b3
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="moduleassemblyname"></a><span data-ttu-id="c1231-102">/moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="c1231-102">/moduleassemblyname</span></span>
<span data-ttu-id="c1231-103">Gibt den Namen der Assembly an, zu der dieses Modul gehört.</span><span class="sxs-lookup"><span data-stu-id="c1231-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1231-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1231-104">Syntax</span></span>  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1231-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="c1231-105">Arguments</span></span>  
  
|<span data-ttu-id="c1231-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c1231-106">Term</span></span>|<span data-ttu-id="c1231-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c1231-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="c1231-108">Der Name der Assembly, der dieses Modul gehören wird.</span><span class="sxs-lookup"><span data-stu-id="c1231-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1231-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1231-109">Remarks</span></span>  
 <span data-ttu-id="c1231-110">Der Compiler verarbeitet die `/moduleassemblyname` Option nur, wenn die `/target:module` -Option wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="c1231-110">The compiler processes the `/moduleassemblyname` option only if the `/target:module` option has been specified.</span></span> <span data-ttu-id="c1231-111">Dies bewirkt, dass der Compiler ein Modul zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1231-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="c1231-112">Das vom Compiler erstellte Modul gilt nur für die Assembly angegeben, mit der `/moduleassemblyname` Option.</span><span class="sxs-lookup"><span data-stu-id="c1231-112">The module created by the compiler is valid only for the assembly specified with the `/moduleassemblyname` option.</span></span> <span data-ttu-id="c1231-113">Setzen Sie das Modul in einer anderen Assembly, treten Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="c1231-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="c1231-114">Die `/moduleassemblyname` Option ist nur erforderlich, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="c1231-114">The `/moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="c1231-115">Ein Datentyp im Modul benötigt Zugriff auf eine `Friend` Typ in einer Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c1231-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="c1231-116">Die referenzierte Assembly hat Freund auf die Assembly gewährt die das Modul erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c1231-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="c1231-117">Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="c1231-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="c1231-118">Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="c1231-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1231-119">Die `/moduleassemblyname` Option ist nicht verfügbar in der Visual Studio Development Environment; es kann nur, wenn Sie von einer Befehlszeile aus kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c1231-119">The `/moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1231-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1231-120">See Also</span></span>  
 <span data-ttu-id="c1231-121">[Gewusst wie: Erstellen einer Mehrfachdateiassembly](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5) </span><span class="sxs-lookup"><span data-stu-id="c1231-121">[How to: Build a Multifile Assembly](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5) </span></span>  
<span data-ttu-id="c1231-122"> [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-122"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c1231-123"> [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-123"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="c1231-124"> [/ main](../../../visual-basic/reference/command-line-compiler/main.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-124"> [/main](../../../visual-basic/reference/command-line-compiler/main.md) </span></span>  
<span data-ttu-id="c1231-125"> [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-125"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="c1231-126"> [/ addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-126"> [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) </span></span>  
<span data-ttu-id="c1231-127"> [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-127"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="c1231-128"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="c1231-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="c1231-129"> [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)</span><span class="sxs-lookup"><span data-stu-id="c1231-129"> [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)</span></span>
