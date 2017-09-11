---
title: / nostdlib (Visual Basic) | Microsoft-Dokumentation
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
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 046e2b845324ed1c2f8c15bbb029fe84f7693f6e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="nostdlib-visual-basic"></a><span data-ttu-id="bfeba-102">/nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfeba-102">/nostdlib (Visual Basic)</span></span>
<span data-ttu-id="bfeba-103">Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.</span><span class="sxs-lookup"><span data-stu-id="bfeba-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfeba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfeba-104">Syntax</span></span>  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="bfeba-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfeba-105">Remarks</span></span>  
 <span data-ttu-id="bfeba-106">Die `/nostdlib` Option entfernt den automatischen Verweis auf die Assembly System.dll und verhindert, dass den Compiler die Datei Vbc.rsp liest.</span><span class="sxs-lookup"><span data-stu-id="bfeba-106">The `/nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="bfeba-107">Die Datei Vbc.rsp – befindet sich im gleichen Verzeichnis wie die Datei Vbc.exe – verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="bfeba-107">The Vbc.rsp file—which is located in the same directory as the Vbc.exe file—references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfeba-108">Die "mscorlib.dll" und "Microsoft.VisualBasic.dll" wird immer verwiesen.</span><span class="sxs-lookup"><span data-stu-id="bfeba-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfeba-109">Die `/nostdlib` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="bfeba-109">The `/nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfeba-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bfeba-110">Example</span></span>  
 <span data-ttu-id="bfeba-111">Der folgende code kompiliert `T2.vb` ohne die Standardbibliotheken zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="bfeba-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="bfeba-112">Müssen Sie festlegen, die `_MYTYPE` Konstante für die bedingte Kompilierung auf die Zeichenfolge "Empty" So entfernen Sie die `My` Objekt.</span><span class="sxs-lookup"><span data-stu-id="bfeba-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfeba-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfeba-113">See Also</span></span>  
 <span data-ttu-id="bfeba-114">[/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="bfeba-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="bfeba-115"> [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="bfeba-115"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="bfeba-116"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="bfeba-116"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="bfeba-117"> [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span><span class="sxs-lookup"><span data-stu-id="bfeba-117"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span></span>
