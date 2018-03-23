---
title: -rootnamespace
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45dce293549674e7e6aac2714e1a7a569719c597
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-rootnamespace"></a><span data-ttu-id="83d5b-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="83d5b-102">-rootnamespace</span></span>
<span data-ttu-id="83d5b-103">Gibt einen Namespace für alle Typdeklarationen an.</span><span class="sxs-lookup"><span data-stu-id="83d5b-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83d5b-104">Syntax</span></span>  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="83d5b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="83d5b-105">Arguments</span></span>  
  
|<span data-ttu-id="83d5b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="83d5b-106">Term</span></span>|<span data-ttu-id="83d5b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="83d5b-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="83d5b-108">Der Name des Namespace, in dem alle Typdeklarationen für das aktuelle Projekt zu schließen.</span><span class="sxs-lookup"><span data-stu-id="83d5b-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83d5b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83d5b-109">Remarks</span></span>  
 <span data-ttu-id="83d5b-110">Wenn Sie die ausführbare Datei (Devenv.exe) von Visual Studio verwenden, um ein erstelltes Projekt kompilieren in der Visual Studio integrierten Entwicklungsumgebung verwenden `-rootnamespace` zum Angeben des Werts, der die <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="83d5b-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="83d5b-111">Finden Sie unter [Devenv-Befehlszeilenschalter](/visualstudio/ide/reference/devenv-command-line-switches) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="83d5b-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="83d5b-112">Verwenden Sie die common Language Runtime MSIL-Disassembler (`Ildasm.exe`) die Namespacenamen in der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="83d5b-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="83d5b-113">In der integrierten Entwicklungsumgebung von Visual Studio - Rootnamespace festlegen</span><span class="sxs-lookup"><span data-stu-id="83d5b-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="83d5b-114">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="83d5b-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="83d5b-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="83d5b-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="83d5b-116">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="83d5b-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="83d5b-117">3.  Ändern Sie den Wert in der **Stamm-Namespace** Feld.</span><span class="sxs-lookup"><span data-stu-id="83d5b-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83d5b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83d5b-118">Example</span></span>  
 <span data-ttu-id="83d5b-119">Der folgende code kompiliert `In.vb` eingeschlossen sind alle Deklarationen von Typen im Namespace `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="83d5b-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="83d5b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83d5b-120">See Also</span></span>  
 [<span data-ttu-id="83d5b-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="83d5b-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="83d5b-122">Ildasm.exe (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="83d5b-122">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="83d5b-123">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="83d5b-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
