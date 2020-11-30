---
description: -target:exe (C#-Compileroptionen)
title: -target:exe (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
ms.openlocfilehash: ae1706f1ecdd396e24711070d19420faa6d34761
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193761"
---
# <a name="-targetexe-c-compiler-options"></a><span data-ttu-id="ec298-103">-target:exe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ec298-103">-target:exe (C# Compiler Options)</span></span>

<span data-ttu-id="ec298-104">Die Option **-target:exe** bewirkt, dass der Compiler eine ausführbare Konsolenanwendung (EXE) erstellt.</span><span class="sxs-lookup"><span data-stu-id="ec298-104">The **-target:exe** option causes the compiler to create an executable (EXE), console application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec298-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec298-105">Syntax</span></span>  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a><span data-ttu-id="ec298-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ec298-106">Remarks</span></span>  

 <span data-ttu-id="ec298-107">Die Option **-target:exe** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ec298-107">The **-target:exe** option is in effect by default.</span></span> <span data-ttu-id="ec298-108">Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="ec298-108">The executable file will be created with the .exe extension.</span></span>  
  
 <span data-ttu-id="ec298-109">Verwenden Sie [-target:winexe](./target-winexe-compiler-option.md), um ein ausführbares Windows-Programm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec298-109">Use [-target:winexe](./target-winexe-compiler-option.md) to create a Windows program executable.</span></span>  
  
 <span data-ttu-id="ec298-110">Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="ec298-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="ec298-111">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die EXE-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec298-111">When specified at the command line, all files up to the next **-out** or **-target:module** option are used to create the .exe file</span></span>  
  
 <span data-ttu-id="ec298-112">Nur eine **Main**-Methode wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ec298-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="ec298-113">Sollte Ihr Code mehr als eine Klasse mit einer **Main**-Methode haben, können Sie mit der Compileroption [-main](./main-compiler-option.md) angeben, welche Klasse die Methode **Main** enthält.</span><span class="sxs-lookup"><span data-stu-id="ec298-113">The [-main](./main-compiler-option.md) compiler option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ec298-114">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="ec298-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ec298-115">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ec298-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="ec298-116">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="ec298-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="ec298-117">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="ec298-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="ec298-118">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec298-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec298-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec298-119">Example</span></span>  

 <span data-ttu-id="ec298-120">Jede der folgenden Befehlszeilen wird `in.cs` kompilieren, wodurch `in.exe` erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="ec298-120">Each of the following command lines will compile `in.cs`, creating `in.exe`:</span></span>  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec298-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec298-121">See also</span></span>

- [<span data-ttu-id="ec298-122">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ec298-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="ec298-123">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="ec298-123">C# Compiler Options</span></span>](./index.md)
