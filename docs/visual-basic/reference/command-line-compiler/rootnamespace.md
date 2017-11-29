---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6b5da8e5eacacde9de5bdc54ef2d5e4d7f0d2653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="4e533-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="4e533-102">/rootnamespace</span></span>
<span data-ttu-id="4e533-103">Gibt einen Namespace für alle Typdeklarationen an.</span><span class="sxs-lookup"><span data-stu-id="4e533-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e533-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e533-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e533-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4e533-105">Arguments</span></span>  
  
|<span data-ttu-id="4e533-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4e533-106">Term</span></span>|<span data-ttu-id="4e533-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4e533-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="4e533-108">Der Name des Namespace, in dem alle Typdeklarationen für das aktuelle Projekt zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4e533-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e533-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e533-109">Remarks</span></span>  
 <span data-ttu-id="4e533-110">Wenn Sie die ausführbare Datei (Devenv.exe) von Visual Studio verwenden, um ein erstelltes Projekt kompilieren in der Visual Studio integrierten Entwicklungsumgebung verwenden `/rootnamespace` zum Angeben des Werts, der die <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4e533-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="4e533-111">Finden Sie unter [Devenv-Befehlszeilenschalter](/visualstudio/ide/reference/devenv-command-line-switches) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4e533-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="4e533-112">Verwenden Sie die common Language Runtime MSIL-Disassembler (`Ildasm.exe`) die Namespacenamen in der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="4e533-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="4e533-113">Zum Festlegen von/RootNamespace in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="4e533-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4e533-114">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4e533-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4e533-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4e533-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="4e533-116">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="4e533-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="4e533-117">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="4e533-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="4e533-118">3.  Ändern Sie den Wert in der **Stamm-Namespace** Feld.</span><span class="sxs-lookup"><span data-stu-id="4e533-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4e533-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e533-119">Example</span></span>  
 <span data-ttu-id="4e533-120">Der folgende code kompiliert `In.vb` eingeschlossen sind alle Deklarationen von Typen im Namespace `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="4e533-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e533-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e533-121">See Also</span></span>  
 [<span data-ttu-id="4e533-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="4e533-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4e533-123">Ildasm.exe (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="4e533-123">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="4e533-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="4e533-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
