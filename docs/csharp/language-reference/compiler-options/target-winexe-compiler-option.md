---
description: -target:winexe (C#-Compileroptionen)
title: -target:winexe (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 6e14a2aac427c7adfd69f66eaf624816b75f6ea2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168932"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="937b3-103">-target:winexe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="937b3-103">-target:winexe (C# Compiler Options)</span></span>

<span data-ttu-id="937b3-104">Die Option **-target:winexe** bewirkt, dass der Compiler ein ausführbares Windows-Programm (EXE) erstellt.</span><span class="sxs-lookup"><span data-stu-id="937b3-104">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="937b3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="937b3-105">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="937b3-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="937b3-106">Remarks</span></span>  

 <span data-ttu-id="937b3-107">Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="937b3-107">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="937b3-108">Windows-Programme stellen eine Benutzeroberfläche immer aus der .NET-Bibliothek oder mithilfe von Windows-APIs bereit.</span><span class="sxs-lookup"><span data-stu-id="937b3-108">A Windows program is one that provides a user interface from either the .NET library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="937b3-109">Verwenden Sie [-target:exe](./target-exe-compiler-option.md), um eine Konsolenanwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="937b3-109">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="937b3-110">Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="937b3-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="937b3-111">Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder [-target](./target-compiler-option.md) verwendet, um das Windows-Programm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="937b3-111">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="937b3-112">Nur eine **Main**-Methode wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="937b3-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="937b3-113">Sollte Ihr Code mehr als eine Klasse mit einer **Main**-Methode enthalten, können Sie mit der Option [-main](./main-compiler-option.md) angeben, welche Klasse die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="937b3-113">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="937b3-114">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="937b3-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="937b3-115">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="937b3-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="937b3-116">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="937b3-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="937b3-117">Ändern Sie die Eigenschaft **Ausgabetyp**.</span><span class="sxs-lookup"><span data-stu-id="937b3-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="937b3-118">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="937b3-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="937b3-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="937b3-119">Example</span></span>  

 <span data-ttu-id="937b3-120">Kompilieren Sie `in.cs` in ein Windows-Programm:</span><span class="sxs-lookup"><span data-stu-id="937b3-120">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="937b3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="937b3-121">See also</span></span>

- [<span data-ttu-id="937b3-122">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="937b3-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="937b3-123">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="937b3-123">C# Compiler Options</span></span>](./index.md)
