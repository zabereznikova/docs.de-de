---
title: -target:exe (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: 194e4f7efaebd9523791090bcab09c019f8554a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="dceaf-102">-target:exe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="dceaf-102">-target:exe (C# Compiler Options)</span></span>
<span data-ttu-id="dceaf-103">Die Option **-target:exe** bewirkt, dass der Compiler eine ausführbare Konsolenanwendung (EXE) erstellt.</span><span class="sxs-lookup"><span data-stu-id="dceaf-103">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dceaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dceaf-104">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="dceaf-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dceaf-105">Remarks</span></span>  
 <span data-ttu-id="dceaf-106">Die Option **-target:exe** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dceaf-106">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="dceaf-107">Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="dceaf-107">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="dceaf-108">Verwenden Sie [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), um ein ausführbares Windows-Programm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dceaf-108">Use [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="dceaf-109">Sofern Sie nicht die Option [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="dceaf-109">Unless otherwise specified with the [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="dceaf-110">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die EXE-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dceaf-110">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="dceaf-111">Nur eine **Main**-Methode wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="dceaf-111">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="dceaf-112">Sollte Ihr Code mehr als eine Klasse mit einer **Main**-Methode haben, können Sie mit der Compileroption [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) angeben, welche Klasse die Methode **Main** enthält.</span><span class="sxs-lookup"><span data-stu-id="dceaf-112">The [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="dceaf-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="dceaf-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="dceaf-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="dceaf-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="dceaf-115">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="dceaf-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="dceaf-116">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="dceaf-116">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="dceaf-117">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="dceaf-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dceaf-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dceaf-118">Example</span></span>  
 <span data-ttu-id="dceaf-119">Jede der folgenden Befehlszeilen wird `in.cs` kompilieren, wodurch `in.exe` erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="dceaf-119">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="dceaf-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dceaf-120">See Also</span></span>  
 [<span data-ttu-id="dceaf-121">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="dceaf-121">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="dceaf-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="dceaf-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
