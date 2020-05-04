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
ms.openlocfilehash: 4df4e74fc13c922f51f5b74c3c152bdea28b4431
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005207"
---
# <a name="-rootnamespace"></a><span data-ttu-id="55f7d-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="55f7d-102">-rootnamespace</span></span>
<span data-ttu-id="55f7d-103">Gibt einen Namespace für alle Typdeklarationen an.</span><span class="sxs-lookup"><span data-stu-id="55f7d-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55f7d-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="55f7d-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="55f7d-105">Arguments</span></span>  
  
|<span data-ttu-id="55f7d-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="55f7d-106">Term</span></span>|<span data-ttu-id="55f7d-107">Definition</span><span class="sxs-lookup"><span data-stu-id="55f7d-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="55f7d-108">Der Name des Namespace, in dem alle Typdeklarationen für das aktuelle Projekt eingeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="55f7d-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55f7d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55f7d-109">Remarks</span></span>  
 <span data-ttu-id="55f7d-110">Wenn Sie die ausführbare Visual Studio-Datei (Devenv.exe) verwenden, um ein Projekt zu kompilieren, das in der integrierten Entwicklungsumgebung in Visual Studio erstellt wurde, verwenden Sie `-rootnamespace`, um den Wert der <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>-Eigenschaft anzugeben.</span><span class="sxs-lookup"><span data-stu-id="55f7d-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="55f7d-111">Weitere Informationen finden Sie unter [Devenv-Befehlszeilenparameter](/visualstudio/ide/reference/devenv-command-line-switches).</span><span class="sxs-lookup"><span data-stu-id="55f7d-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="55f7d-112">Verwenden Sie den MSIL-Disassembler der Common Language Runtime (`Ildasm.exe`), um die Namespacenamen in Ihrer Ausgabedatei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="55f7d-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="55f7d-113">So legen Sie -rootnamespace in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="55f7d-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="55f7d-114">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="55f7d-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="55f7d-115">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="55f7d-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="55f7d-116">2.  Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="55f7d-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="55f7d-117">3.  Ändern Sie den Wert im Feld **Stammnamespace** entsprechend.</span><span class="sxs-lookup"><span data-stu-id="55f7d-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="55f7d-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55f7d-118">Example</span></span>  
 <span data-ttu-id="55f7d-119">Der folgende Code kompiliert `In.vb` und schließt alle Typdeklarationen im Namespace `mynamespace` ein.</span><span class="sxs-lookup"><span data-stu-id="55f7d-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="55f7d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55f7d-120">See also</span></span>

- [<span data-ttu-id="55f7d-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="55f7d-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="55f7d-122">Ildasm.exe (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="55f7d-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="55f7d-123">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="55f7d-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
