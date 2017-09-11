---
title: / RootNamespace | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
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
ms.openlocfilehash: 9a7a26407e981d3aea58d970d88bf25025e6bba6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="rootnamespace"></a><span data-ttu-id="7f55d-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="7f55d-102">/rootnamespace</span></span>
<span data-ttu-id="7f55d-103">Gibt einen Namespace für alle Typdeklarationen an.</span><span class="sxs-lookup"><span data-stu-id="7f55d-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f55d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f55d-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="7f55d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="7f55d-105">Arguments</span></span>  
  
|<span data-ttu-id="7f55d-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="7f55d-106">Term</span></span>|<span data-ttu-id="7f55d-107">Definition</span><span class="sxs-lookup"><span data-stu-id="7f55d-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="7f55d-108">Der Name des Namespaces in das alle Typdeklarationen für das aktuelle Projekt eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7f55d-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f55d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f55d-109">Remarks</span></span>  
 <span data-ttu-id="7f55d-110">Wenn Sie die ausführbare Datei (Devenv.exe) von Visual Studio erstellten Projekt kompilieren in der Visual Studio IDE, verwenden `/rootnamespace` zum Angeben des Werts, der die <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>Eigenschaft.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="7f55d-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="7f55d-111">Finden Sie unter [Devenv-Befehlszeilenschalter](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7f55d-111">See [Devenv Command Line Switches](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="7f55d-112">Verwenden Sie die common Language Runtime MSIL-Disassembler (ich`ldasm.exe`) die Namespacenamen in der Ausgabedatei anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f55d-112">Use the common language runtime MSIL Disassembler (I`ldasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="7f55d-113">Zum Festlegen von/RootNamespace in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="7f55d-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7f55d-114">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="7f55d-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7f55d-115">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="7f55d-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="7f55d-116">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="7f55d-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="7f55d-117">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="7f55d-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="7f55d-118">3.  Ändern Sie den Wert in der **Stamm-Namespace** Feld.</span><span class="sxs-lookup"><span data-stu-id="7f55d-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f55d-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f55d-119">Example</span></span>  
 <span data-ttu-id="7f55d-120">Der folgende code kompiliert `In.vb` und alle Typdeklarationen im Namespace `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="7f55d-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f55d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f55d-121">See Also</span></span>  
 <span data-ttu-id="7f55d-122">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f55d-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="7f55d-123"> [Ildasm.exe (IL-Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) </span><span class="sxs-lookup"><span data-stu-id="7f55d-123"> [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) </span></span>  
<span data-ttu-id="7f55d-124"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="7f55d-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
