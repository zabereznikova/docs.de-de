---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: ff4b1729f1b9fb1d698b4b5b1e3711ce3d27b4db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655555"
---
# <a name="-rootnamespace"></a><span data-ttu-id="f51b0-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="f51b0-102">-rootnamespace</span></span>
<span data-ttu-id="f51b0-103">Gibt einen Namespace für alle Typdeklarationen an.</span><span class="sxs-lookup"><span data-stu-id="f51b0-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f51b0-104">Syntax</span></span>  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="f51b0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f51b0-105">Arguments</span></span>  
  
|<span data-ttu-id="f51b0-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f51b0-106">Term</span></span>|<span data-ttu-id="f51b0-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f51b0-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="f51b0-108">Der Name des Namespace, in dem alle Typdeklarationen für das aktuelle Projekt zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f51b0-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f51b0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f51b0-109">Remarks</span></span>  
 <span data-ttu-id="f51b0-110">Wenn Sie die ausführbare Datei (Devenv.exe) von Visual Studio verwenden, um ein erstelltes Projekt kompilieren in der integrierten Entwicklungsumgebung Visual Studio, verwenden `-rootnamespace` zum Angeben des Werts, der die <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f51b0-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="f51b0-111">Finden Sie unter [Devenv-Befehlszeilenschalter](/visualstudio/ide/reference/devenv-command-line-switches) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f51b0-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="f51b0-112">Verwenden Sie die common Language Runtime MSIL Disassembler (`Ildasm.exe`) um die Namespacenamen in Ihrer Ausgabedatei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f51b0-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="f51b0-113">-Rootnamespace in der integrierten Entwicklungsumgebung von Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="f51b0-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f51b0-114">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f51b0-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f51b0-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f51b0-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f51b0-116">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="f51b0-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="f51b0-117">3.  Ändern Sie den Wert in der **Stamm-Namespace** Feld.</span><span class="sxs-lookup"><span data-stu-id="f51b0-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f51b0-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f51b0-118">Example</span></span>  
 <span data-ttu-id="f51b0-119">Der folgende code kompiliert `In.vb` und alle Typdeklarationen im Namespace `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="f51b0-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f51b0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f51b0-120">See also</span></span>

- [<span data-ttu-id="f51b0-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f51b0-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f51b0-122">Ildasm.exe (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="f51b0-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="f51b0-123">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f51b0-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
